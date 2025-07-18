---
title: 노출 횟수 및 상호 작용 이벤트 캡처
description: 노출 및 상호 작용 이벤트를 캡처하고 Journey Optimizer 내에서 보고할 데이터를 준비합니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
recommendations: noDisplay, noCatalog
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# 노출 횟수 및 상호 작용 이벤트 캡처

AJO 오퍼 노출 횟수 및 클릭 수에 대한 보고를 활성화하려면 다음 구성 요소를 구성해야 합니다.
>[!NOTE]
>
> 이러한 필수 구성 요소는 [이전 자습서](https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/create-schema-and-dataset)의 스키마 및 데이터 세트 만들기 섹션에서 이미 완료되었습니다.

## &#x200B;1. Adobe Experience Platform(AEP)의 데이터 세트

- **XDM ExperienceEvent** 스키마를 기반으로 하는 데이터 집합입니다.

스키마에 페이지 URL, 레퍼러 등을 캡처하는 `Web Details` 필드 그룹이 포함되어야 합니다.

## &#x200B;2. 데이터 스트림 구성

- Adobe Experience Platform에서 **데이터 스트림**&#x200B;을(를) 만들어야 합니다.
- 모든 웹 SDK 이벤트가 올바른 대상으로 올바르게 수집되도록 하려면 이 데이터 스트림을 위에 구성된 데이터 세트에 연결해야 합니다.

## &#x200B;3. Adobe Experience Platform 태그 속성

- 이전 단계에서 생성한 데이터 스트림을 사용하도록 AEP Web SDK 확장이 구성되었습니다.
- Experience Cloud ID 서비스 구성됨
- ECID라는 데이터 요소가 속성에 추가됩니다
- 오퍼가 렌더링되는 사이트에서 구현됩니다.


오퍼 성능에 대한 보고를 활성화하기 위한 첫 번째 단계는 오퍼가 표시될 때(노출 횟수) 및 클릭할 때(상호 작용)를 캡처하는 것입니다. 이러한 이벤트는 참여를 측정하고, 클릭스루 비율을 계산하고, Adobe Experience Platform 내의 오퍼 효과를 분석할 수 있는 기반을 제공합니다.

alloy(&quot;sendEvent&quot;) 함수는 Adobe Journey Optimizer(AJO)에서 반환된 오퍼와 사용자 상호 작용을 기록하는 데 사용됩니다.

sendEvent 페이로드는 이벤트 유형(노출에 대해서는 decisioning.propositionDisplay, 클릭에 대해서는 decisioning.propositionInteract), 고유한 이벤트 ID, 타임스탬프 및 사용자 ID(identityMap)를 포함하여 오퍼 상호 작용을 캡처합니다. 또한 표시되거나 클릭한 오퍼(제안) 목록과 함께 추적 토큰을 포함하여 정확한 속성을 보장합니다. 이 구조를 통해 Adobe Journey Optimizer에서 개인화된 오퍼 성능을 보고 및 최적화할 수 있습니다.

두 가지 유형의 상호 작용 이벤트가 캡처됩니다.

## 노출 이벤트

노출은 오퍼가 페이지에 렌더링되어 사용자에게 표시될 때 발생합니다. 이벤트는 decisioning.propositionDisplay 이벤트 유형을 사용하여 추적됩니다.


```javascript
 alloy("sendEvent", {
            xdm: {
              _id: generateUUID(),
              timestamp: new Date().toISOString(),
              eventType: "decisioning.propositionDisplay",
              identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "authenticated",
                      primary: true
                    }]
                  },
              _experience: {
                decisioning: {
                  propositionEventType: {
                    display: 1
                  },
                  
                   propositions: window.latestPropositions
                  
                }
              }
            }
          });
        }
```

## 오퍼 상호 작용

상호 작용은 사용자가 렌더링된 오퍼 내에서 call-to-action(CTA)를 클릭할 때 기록됩니다. 이벤트는 decisioning.propositionInteract 이벤트 유형을 사용하여 추적됩니다.

```javascript
alloy("sendEvent", {
                xdm: {
                  _id: generateUUID(),
                  timestamp: new Date().toISOString(),
                  eventType: "decisioning.propositionInteract",
                  identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "ambiguous",
                      primary: true
                    }]
                  },
                  _experience: {
                    decisioning: {
                      propositionEventType: {
                        interact: 1
                      },
                      propositionAction: {
                        id: offerId,
                        tokens: [trackingToken]
                      },
                       propositions: window.latestPropositions
                    }
                  }
                }
              })
```

클릭 및 노출 이벤트에 제안을 포함하는 것은 Adobe Journey Optimizer에서 정확한 오퍼 보고를 위해 필수적입니다. 이러한 제안은 사용자에게 제공된 정확한 오퍼를 나타내므로 Adobe은 사용자 상호 작용(예: 노출 횟수 또는 클릭 수)을 시스템에서 결정한 특정 결정으로 다시 연결할 수 있습니다.

제안 내의 각 오퍼에는 Adobe에서 생성한 고유 식별자인 추적 토큰이 포함됩니다. 이 토큰은 해당 클릭 또는 노출 이벤트에서 받은 그대로(변경 없이) 전달되어야 합니다. 추적 토큰을 일치시키면 Adobe은 사용자 작업을 올바른 오퍼 의사 결정과 정확하게 연결하여 다운스트림 보고 및 AI 기반 최적화를 가능하게 합니다.
