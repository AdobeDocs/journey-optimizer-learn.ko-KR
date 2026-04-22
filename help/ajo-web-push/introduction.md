---
title: AJO의 웹 푸시
description: 이 자습서에서는 Adobe Journey Optimizer(AJO)를 사용하여 웹 푸시 알림을 구현하는 방법을 보여줍니다. 웹 SDK으로 사용자 옵트인을 캡처하고, 예약된 캠페인을 통해 알림을 보내고, AEP 태그와 함께 사용자 지정 price.drop 이벤트를 사용하여 실시간 푸시 메시지를 트리거하는 방법에 대해 알아봅니다.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Adobe Journey Optimizer의 웹 푸시

웹 푸시 알림은 실시간으로 사용자를 다시 참여시키는 강력한 방법이며 이 튜토리얼에서는 Adobe Journey Optimizer(AJO)를 사용하여 사용자를 구현하는 방법을 안내합니다. 먼저 웹 SDK을 사용하여 푸시 알림에 대한 사용자 옵트인 환경 설정을 캡처하여 원활하고 규정 준수 구독 환경을 보장합니다. 다음으로, 선택한 사용자에게 푸시 알림을 전송하는 캠페인을 만들어 대상자 기반 참여를 활성화합니다. 마지막으로, AEP 태그를 활용하여 AJO에서 여정을 시작하고 실시간 사용자 행동을 기반으로 개인화된 푸시 알림을 적시에 전달하는 사용자 지정 가격 하락 이벤트를 트리거하는 방법에 대해 알아봅니다.

사용자가 알림을 옵트인할 수 있도록 하는 샘플 웹 페이지

![enable-notifications](assets/enable-notifications.png)

가격 하락 이벤트를 트리거하는 샘플 웹 페이지

![가격 하락 트리거](assets/trigger-price-drop-event.png)

## 전제 조건

이 튜토리얼은 실습이 가능하고 따라하기 쉽도록 설계되었습니다. 깊이 있는 전문 지식은 필요하지 않지만 다음 개념에 대한 기본 지식이 도움이 될 것입니다.

- Adobe Journey Optimizer(여정 또는 캠페인 만들기)
- AEP 데이터 수집(태그) 및 웹 SDK
- 스키마 및 이벤트와 같은 기본 Adobe Experience Platform 개념
- 일부 JavaScript 및 일반 웹 개발 개념
- 기본 Node.js 지식(VAPID 키 생성 및 단순 구성 끝점 제공용)

이러한 영역을 처음 사용하는 경우 걱정하지 마십시오. 튜토리얼에서는 주요 단계를 안내합니다.
이 자습서에서는 엔드 투 엔드 웹 푸시 알림 사용 사례를 구현하는 데 중점을 두고 있으므로 위의 도구 및 개념에 대한 작업 지식을 통해 효과적으로 따를 수 있습니다.


## 🔔 브라우저 알림 사용

알림이 차단되거나 표시되지 않는 경우 브라우저 설정에서 활성화해야 할 수 있습니다. 아래 안내서를 참조하십시오.

- **Google Chrome(Windows/macOS)**\
  <https://support.google.com/chrome/answer/3220216>

- **Microsoft Edge(Windows)**\
  <https://support.microsoft.com/en-us/microsoft-edge/manage-website-notifications-in-microsoft-edge>

- **Safari(macOS)**\
  <https://support.apple.com/guide/safari/customize-website-notifications-sfri40734/mac>

- **Safari(iPhone/iPad)**\
  <https://support.apple.com/en-us/HT213893>


## 샘플 애플리케이션


도움이 되도록 전체 샘플 애플리케이션을 사용할 수 있습니다.

- [라이브 데모 - 옵트인:](https://ajo-web-push.onrender.com/)

- [가격 하락 이벤트 트리거:](https://ajo-web-push.onrender.com/price-drop-trigger.html)

- [Source 코드:](https://github.com/gbedekar489/ajo-web-push)

라이브 데모를 탐색하여 플로우 인 액션을 보거나 저장소를 복제하여 프로젝트를 로컬로 실행할 수 있습니다.

