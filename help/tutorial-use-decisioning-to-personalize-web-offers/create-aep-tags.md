---
title: Adobe Experience Platform 태그 만들기
description: 사용자 투자 환경 설정(주식, 채권, CD)을 기반으로 AJO 대상 만들기
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Adobe Experience Platform 태그 만들기

Experience Platform 태그는 Adobe Experience Platform Web SDK을 로드하도록 웹 페이지에 구성되어 있으므로 sendEvent API 호출이 개인화된 경험을 트리거할 수 있습니다. 이 설정을 사용하면 필요한 클라이언트측 라이브러리가 올바르게 초기화되어 오퍼 전달을 위해 Adobe Journey Optimizer과 실시간 상호 작용할 수 있습니다.

1. 데이터 수집에 로그인합니다.
1. **[!UICONTROL 태그]** > **[!UICONTROL 새 속성]**&#x200B;을 클릭합니다.
1. ECID 서비스라는 Adobe Experience Platform 태그를 만듭니다.
1. 태그에 다음 확장을 추가합니다.

   ![tags-extensions](assets/ecid-tag.png)

1. 이전 자습서에서 만든 Financial Advisor 데이터 스트림과 올바른 환경을 사용하도록 Adobe Experience Platform Web SDK을 구성합니다

   ![web-sdk-configuration](assets/web-sdk-configuration.png)

Adobe 클라이언트 데이터 레이어 및 코어 확장에 대한 추가 구성은 필요하지 않습니다

## 데이터 요소 만들기

Experience Platform 태그의 ECID 데이터 요소는 디버깅 및 테스트 목적으로만 만들어집니다. 데이터 요소를 사용하면 개발자가 사용자의 브라우저 세션에 할당된 Experience Cloud ID를 볼 수 있으므로 ID 결합의 유효성을 검사하고 `sendEvent` 호출이 올바른 프로필과 연결되어 있는지 확인할 수 있습니다. 이 요소는 개인화가 작동하는 데 필요하지 않지만 구현 및 QA 중에 유용합니다

![ecid](assets/ecid-data-element.png)


## HTML 페이지에 AEP 태그 포함

Adobe Experience Platform 태그를 빌드하고 게시합니다.

AEP Tags 속성이 게시되면 Adobe은 HTML ``` <head>``` 내부 또는 ``` <body>``` 태그의 맨 아래에 배치해야 하는 스크립트 태그를 제공합니다.

1. 태그(ECID 서비스) 속성으로 이동합니다.

1. 환경 을 클릭한 다음 원하는 환경의 설치 아이콘(예: 개발, 스테이징, 프로덕션)을 클릭합니다.

1. 포함된 코드를 확인합니다.

   이 코드는 HTML 페이지에서 ```</body>``` 태그를 닫기 바로 앞에 배치해야 합니다.
