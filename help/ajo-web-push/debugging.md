---
title: AJO에서 웹 푸시 디버깅
description: 이 페이지에서는 웹 SDK 요청 확인을 포함하여 웹 푸시 알림 흐름을 디버깅하는 데 유용한 팁을 제공합니다.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# AJO에서 웹 푸시 디버깅

이 페이지에서는 웹 SDK 요청 확인, AEP에서 ECID 및 사용자 프로필 확인, price.drop 등의 이벤트가 올바르게 송수신되는지 확인하는 등 웹 푸시 알림 플로우를 디버깅하는 데 유용한 팁을 제공합니다.

- **Adobe Experience Platform Debugger(Chrome 확장) 사용**\
  웹 SDK 활동을 보다 쉽게 검사하려면 [Chrome용 AEP Debugger 확장 프로그램](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob)을 설치하십시오.

이 도구를 사용하면 다음 작업을 수행할 수 있습니다.
- 웹 SDK 요청 및 응답 보기\
- ECID 확인(Experience Cloud ID)\
- 데이터 스트림 구성 및 페이로드의 유효성 검사

- **사용자가 식별되었는지 확인(ECID)**\
  AEP Debugger 또는 브라우저 콘솔을 사용하여 ECID가 생성되었는지 확인합니다. 이 ID는 AEP 및 AJO에서 사용자를 추적하는 데 사용됩니다.

- **네트워크 탭을 사용하여 요청을 확인합니다**\
  브라우저의 개발자 도구에서 **네트워크 탭**&#x200B;을(를) 열고 웹 SDK에서 수행한 요청을 필터링합니다(`/collect` 또는 `interact` 찾기).
   - 페이지가 로드되고 작업이 트리거될 때 확인 요청이 전송됨
   - `price.drop` 이벤트가 페이로드에 포함되어 있는지 확인합니다.

- **AEP에서 사용자 프로필 조회**\
  ECID를 사용하여 Adobe Experience Platform에서 사용자 프로필을 검색합니다. 이렇게 하면 사용자가 인식되고 해당 데이터(예: 푸시 구독)가 올바르게 저장되는지 확인하는 데 도움이 됩니다.

- **`price.drop` 이벤트가 수신되었는지 확인**\
  웹 페이지에서 이벤트를 트리거한 후 이벤트가 수집되고 동일한 ECID와 연결되었는지 AEP에서 확인합니다.
`feedback.status`에 대한 message.feedback 이벤트의 json을 확인하십시오. 상태 값은 `sent`이어야 합니다.
  ![가격 하락](assets/price-drop-profile-event.png)

- **푸시 알림이 활성화되었는지 확인**\
  다음을 확인합니다.
   - 사용자가 브라우저 알림 프롬프트를 수락했습니다.
   - 푸시 토큰이 사용자 프로필에 있습니다.

- **여정 설정 확인**\
  여정이 게시되었고 `price.drop` 이벤트를 수신하도록 구성되어 있는지 확인하십시오.

