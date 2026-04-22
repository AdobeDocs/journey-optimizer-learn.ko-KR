---
title: 여정에서 푸시 메시지 보내기
description: Adobe Journey Optimizer의 빈도 제한은 개별 오퍼 수준에서 적용되며, 오퍼 노출과 클릭 이벤트를 모두 캡처하는 데 의존합니다. 이렇게 하려면 Adobe Web SDK을 사용하여 tracking decisioning.propositionDisplay 및 decisioning.propositionInteract 이벤트를 만들고 Adobe Experience Platform에서 업데이트된 XDM 경험 이벤트 스키마에 매핑해야 합니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# 여정에서 푸시 메시지 보내기

가격 하락 이벤트를 기반으로 여정을 트리거하면 행동별로 실시간으로 사용자를 참여시킬 수 있습니다. 실제 시나리오에서 이 이벤트는 일반적으로 제품 가격이 업데이트될 때 백엔드 가격 책정 시스템에서 발생합니다. 이 자습서에서는 이름 및 SKU와 같은 제품 세부 사항을 포함하여 AEP 태그를 사용하여 Adobe 데이터 레이어를 통해 사용자 지정 price.drop 이벤트를 전송하여 해당 비헤이비어를 시뮬레이션합니다. 이 이벤트는 Adobe Experience Platform에 수집되어 Adobe Journey Optimizer의 여정에 대한 시작 트리거로 사용됩니다. 수신이 완료되면 여정은 적격 사용자에게 개인화된 푸시 알림을 즉시 전송하여 가격 하락에 대해 알리고 적시에 조치를 취할 수 있습니다.

사용자 지정 이벤트를 사용하여 여정을 트리거하는 절차는 다음과 같습니다

## Journey Optimizer에서 사용자 지정 이벤트 만들기

Adobe Journey Optimizer에 로그인하고 관리 → 구성 → 이벤트로 이동한 다음 이벤트 생성을 선택합니다. PriceDropEvent라는 새 이벤트를 만들고 이 이벤트를 자습서에서 이전에 만든 이벤트 스키마 SchemaForPushNotification과 연결합니다. 이벤트 속성이 참조 이미지에 표시된 대로 구성되었는지 확인합니다.

![event-properties](assets/price-drop-event.png)

스키마에서 필수 필드를 선택하여 개인화에 사용할 수 있도록 합니다. 특히 ProductListItems 개체의 `Name` 및 `SKU`과(와) identityMap의 식별자를 포함합니다. 그런 다음 개인화 편집기 내에서 이러한 필드에 액세스할 수 있으므로 제품 및 사용자 컨텍스트를 기반으로 푸시 알림 메시지를 동적으로 작성할 수 있습니다.

## 태그 속성 만들기

이 속성은 자습서에서 이전에 만든 WebPushDataStream에 연결된 AEP Web SDK으로 구성됩니다. 태그 속성은 Adobe 데이터 레이어에서 price.drop 이벤트를 수신하고 ProductListItems 데이터 요소를 업데이트하여 관련 제품 세부 사항을 매핑합니다. 데이터가 준비되면 태그 속성의 규칙이 실행되고, Web SDK을 통해 price.drop 이벤트를 AEP으로 보냅니다. 그런 다음 이 이벤트는 Adobe Journey Optimizer에서 여정의 진입점 역할을 하므로 가격 하락에 따라 푸시 알림을 즉시 전달할 수 있습니다.



