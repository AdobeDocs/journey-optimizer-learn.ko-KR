---
title: 충성도 상태 환영 이메일 만들기 - 문제
description: 여정 캔버스에서 여정을 작성하는 기본적인 방법을 이해합니다.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
source-git-commit: 957515149af1281d29a45b24ca499ef097656eb8
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 8%

---


# 충성도 상태 환영 이메일 만들기 - 문제

![AJO 충성도 상태 환영 이메일 - 챌린지 배너](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 과제 | 충성도 상태 시작 이메일 만들기 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[메시지 편집기로 이메일 콘텐츠 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[개인화에 컨텍스트 기반 이벤트 정보 사용](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[개인화에 도우미 기능 사용](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| 다운로드할 자산 | [주문 확인 자산](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## 더 스토리

Luma는 고객을 유치하고 유지하는 방법으로 충성도 프로그램을 제공합니다. 프로그램은 네 가지 다른 수준을 제공합니다. 은, 금, 백금, 그리고 다이아몬드입니다.

각 충성도 계층은 반복 사업에 대한 보상으로 다양한 수준 또는 보상, 할인 및 기타 특별 혜택을 받습니다.

특수 다이아몬드 상태에 밑줄을 긋습니다. Luma는 다이아몬드 계층에 도달하면 고객에게 환영 이메일을 보내려고 합니다.

## 과제

다이아몬드 충성도 계층에 도달하면 고객에게 자동으로 환영 이메일을 보내는 여정을 설정해야 했습니다.

>[!NOTE]
> 공유 교육 샌드박스에서 작업 중인 경우, 만든 요소의 이름에 사전 수정 사항으로 이름 또는 이니셜을 추가하는 것이 좋습니다.

### Luma 다이아몬드 상태 세그먼트를 만듭니다.

Journey Optimizer에서 **이름 - Luma - 다이아몬드 상태**.

### Luma - 새 상태 - 다이아몬드 - 트랜잭션 이메일 메시지 만들기

환영 이메일 메시지 만들기

1. 라는 이름의 트랜잭션 이메일 메시지를 만듭니다 `(your name)_Luma – New Status – Diamond – Transactional email message`.
2. 전자 메일에 제목란 지정 `Welcome to Diamond Status, (recipient's first name)!`.
3. 제공된 HTML 파일 사용 **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** 이메일 본문에 사용됩니다.


### **여정 #3 - 다이아몬드 상태 업그레이드 시작 이메일**

충성도 고객이 새로운 계층으로 이동하여 축하하고 새로운 이점을 알려면 이메일을 보냅니다.

1. 고객이 다이아몬드 새 충성도 계층(특히 고객이 새 다이아몬드 수준 멤버에 대해 정의된 세그먼트를 입력할 때)으로 이동하여 &quot;Luma - 새 상태 - 다이아몬드 - 트랜잭션&quot; 이메일을 보낼 때 트리거되는 여정을 만듭니다
2. 완료되면 여정을 테스트 모드로 전환하고 여정을 트리거하여 직접 보냅니다  

성공 기준

개인화된 &quot;Luma - 새 상태 - 다이아몬드-트랜잭션&quot; 이메일을 수신해야 합니다.