---
title: AI 모델 교육을 위한 Adobe Web SDK으로 오퍼 상호 작용 캡처
description: 이 문서에서는 Adobe Experience Platform Web SDK(alloy.js)를 사용하여 오퍼 노출 횟수 및 클릭 수와 같은 사용자 상호 작용 데이터를 캡처하는 방법에 대한 지침을 제공합니다. 이 데이터는 Adobe Journey Optimizer(AJO)에서 AI 모델을 지능적으로 학습시켜 사용자 행동과 상황별 신호에 따라 오퍼의 순위를 매기는 데 기반이 됩니다.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
exl-id: 3cb280b3-71e5-4e91-9252-5679d794d4c4
source-git-commit: 6c4f33d1f55be298781cfb0958862f9710e3647a
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---

# AI 모델 교육을 위한 Adobe Web SDK으로 오퍼 상호 작용 캡처

>[!NOTE]
>
> Adobe Journey Optimizer에서 AI 기반 순위 방법을 사용하여 예측된 참여를 기반으로 표시되는 오퍼를 개인화할 경우에만 이 문서를 완료하십시오.



이 문서에서는 JavaScript 코드에서 직접 alloy(&quot;sendEvent&quot;, ...)를 호출하여 Adobe Experience Platform Web SDK을 사용하여 오퍼 상호 작용 이벤트(노출 횟수 또는 클릭 수 등)를 캡처하는 방법을 보여 줍니다. 이 데이터는 AEP에 수집되어 실시간 행동을 기반으로 보다 스마트한 오퍼 순위를 위해 Adobe Journey Optimizer(AJO)의 AI 모델을 교육하는 데 사용됩니다.

Adobe Journey Optimizer에서 오퍼 순위에 대한 AI 모델을 만들려면, 데이터 세트가 제안 상호 작용 필드 그룹을 포함하는 스키마를 기반으로 해야 합니다. 이 필드 그룹은 decisioning.propositionDisplay 및 decisioning.propositionInteract와 같은 주요 의사 결정 이벤트와 함께 containedPropositions, display 및 interact와 같은 필수 필드를 지원합니다.

이를 위해서는 두 가지 유효한 접근 방식이 있습니다.

- 상호 작용 추적을 위해 특별히 구성된 새 스키마, 데이터 세트 및 데이터 스트림 만들기
- 기존 스키마 업데이트 - 이 자습서에서 수행하는 작업



## 오퍼 상호 작용 이벤트를 캡처하도록 기존 스키마 업데이트

새 스키마를 만드는 대신 날씨 관련 오퍼에 사용된 기존 경험 이벤트 스키마가 상호 작용 추적을 지원하도록 업데이트됩니다.

Adobe Experience Platform:

- 날씨 기반 오퍼에 사용 중인 기존 _**날씨 스키마**_ 경험 이벤트 스키마를 엽니다.

- 필드 그룹 추가:
경험 이벤트 - 제안 상호 작용

새 데이터 세트나 데이터 스트림을 만들 필요가 없습니다. 날씨 오퍼에 대한 기존 설정을 계속 사용하십시오. 전송된 이벤트는 AI 모델 교육 및 오퍼 성과 추적에 대한 Adobe Journey Optimizer의 기대에 부합합니다.


현재 데이터 세트를 계속 사용(새 데이터 세트를 만들 필요 없음)

기존 데이터 스트림이 이미 구성되어 있고 Adobe Experience Platform 태그 속성에서 사용 중입니다. 변경 사항이 필요하지 않습니다.

웹 SDK은 새 상호 작용 이벤트를 올바른 대상으로 자동으로 라우팅합니다.

이렇게 간소화된 설정을 통해 모든 의사 결정 및 날씨 이벤트를 단일 통합 데이터 세트로 수집할 수 있으므로 Adobe Journey Optimizer의 AI 모델을 교육하는 데 이상적입니다.


## 오퍼 표시 이벤트 캡처(노출 횟수)

오퍼의 HTML 구조가 사용자가 오퍼에 참여할 수 있도록 대화형 요소(특히 `<a>` 및 `<button>` 태그)를 포함하도록 수정되었습니다(예: &quot;오퍼 클레임&quot; 또는 &quot;자세히 알아보기&quot; 버튼).

각 버튼에는 data-offer-id 속성이 포함되어 있으므로 해당 상호 작용을 적절하게 추적할 수 있습니다.



오퍼가 사용자에게 표시될 때 기록하기 위해 날씨 오퍼를 렌더링하는 데 사용된 기존 JavaScript 파일이 디스플레이 이벤트 추적을 포함하도록 업데이트되었습니다.

이제 하나 이상의 오퍼가 표시되면 decisioning.propositionDisplay 이벤트가 Adobe Web SDK(alloy.sendEvent)를 사용하여 전송됩니다. 이 이벤트에는 필수 표시인 1 플래그가 포함되어 있으며 관련 제안을 참조합니다.


```javascript
alloy("sendEvent", {
                    xdm: {
                      _id: generateUUID(),
                      timestamp: new Date().toISOString(),
                      eventType: "decisioning.propositionInteract",
                      identityMap: {
                        ECID: [{
                          id: ecidValue,
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
                  });
```

## 오퍼 클릭 이벤트 캡처(상호 작용)

사용자가 오퍼를 클릭하는 시점을 추적하기 위해 오퍼 컨테이너 내에 렌더링된 `<a>` 및 `<button>` 요소 모두에서 클릭을 수신하도록 기존 JavaScript을 업데이트했습니다.

클릭이 감지되면 Adobe Web SDK을 사용하여 decisioning.propositionInteract 이벤트가 전송됩니다. 이벤트에는 필요한 상호 작용: 1 플래그가 포함되어 있으며 특정 오퍼 ID 및 의사 결정 범위를 참조합니다.

```javascript
// Attach click tracking to <a> and <button> elements
child.querySelectorAll("a, button").forEach(el => {
                el.addEventListener("click", () => {
                  const ecidValue = getECID();
                  if (!ecidValue || !offerId || !trackingToken) {
                    console.warn("Girish!!!!  Missing ECID, offerId, or trackingToken. Interaction event not sent.");
                    return;
                  }

                  alloy("sendEvent", {
                    xdm: {
                      _id: generateUUID(),
                      timestamp: new Date().toISOString(),
                      eventType: "decisioning.propositionInteract",
                      identityMap: {
                        ECID: [{
                          id: ecidValue,
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
                  });
                });
              });
```

## Adobe Journey Optimizer Offer Decisioning에서 오퍼 순위에 대한 AI 모델 만들기

이제 웹 SDK을 통해 캡처하고 Adobe Experience Platform에 저장된 오퍼 노출 횟수 및 클릭 수를 통해 이 데이터를 사용하여 참여를 유도할 가능성이 가장 높은 오퍼를 예측하는 AI 모델을 교육할 수 있습니다.

이 AI 모델은 순위 공식이나 선택 전략에서 참조되어 각 사용자에 대해 우선 순위가 지정된 오퍼를 결정합니다.
- Journey Optimizer에 로그인
- 의사 결정 -> 전략 설정 -> AI 모델 ->AI 모델 만들기 로 이동합니다.
- 올바른 데이터 세트를 사용해야 합니다.
  ![ai-모델](assets/ai-model.png)
- AI 모델을 저장하고 활성화합니다.
- 이전 단계에서 만든 선택 전략을 업데이트하여 순위 지정 방법에 AI 모델 사용
  ![update-selection-strategy](assets/update-selection-strategy.png)

## 솔루션 테스트

[기존 웹 페이지](assets/ai-model.js)에 [업데이트된 JavaScript 파일](assets/weather-offers.html) 포함
