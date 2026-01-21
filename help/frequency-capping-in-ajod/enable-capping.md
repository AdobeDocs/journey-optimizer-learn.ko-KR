---
title: AJO 캠페인에 대한 빈도 제한 활성화
description: Adobe Journey Optimizer의 빈도 제한은 개별 오퍼 수준에서 적용되며, 오퍼 노출과 클릭 이벤트를 모두 캡처하는 데 의존합니다. 이렇게 하려면 Adobe Web SDK을 사용하여 tracking decisioning.propositionDisplay 및 decisioning.propositionInteract 이벤트를 만들고 Adobe Experience Platform에서 업데이트된 XDM 경험 이벤트 스키마에 매핑해야 합니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# AJO 캠페인에 대한 빈도 제한 활성화

오퍼에 빈도 제한을 적용하려면 다음 단계를 완료하십시오.

## 이벤트 스키마 업데이트

* 표시된 대로 필드 그룹을 추가하여 기존 이벤트 스키마를 업데이트합니다.
* ![이벤트 스키마](assets/schema.png)

## 오퍼에 대한 빈도 제한 업데이트


* ![오퍼](assets/offer-capping.png)

## 오퍼에 추적 토큰 추가

대체 오퍼를 추가하여 캠페인에 사용된 결정 정책 편집
![대체 ](assets/fallback.png)

왼쪽 탐색에서 결정 정책 아이콘을 클릭하고 결정 트리를 드릴다운하여 itemID 및 trackingToken을 선택하여 trackingToken 및 ItemID를 추가할 수 있습니다.

아래와 같이 오퍼를 포함하는 div에 항목 ID 및 추적 토큰을 추가합니다
![id-and-tracking-token](assets/id-and-tracking-token.png)

이렇게 하면 렌더링된 각 오퍼에 정확한 노출 및 클릭 이벤트 추적에 필수적인 데이터 추적 토큰이 포함됩니다.


수정된 캠페인을 활성화합니다.


## 노출 및 추적 이벤트 보내기

기존 JavaScript 코드를 수정하여 Adobe Web SDK을 사용하여 오퍼 노출 및 상호 작용 이벤트를 캡처하고 Adobe Experience Platform에 보냅니다. 여기에 제공된 [샘플 코드를 참조하세요.](capture-impression-click-events.md)


