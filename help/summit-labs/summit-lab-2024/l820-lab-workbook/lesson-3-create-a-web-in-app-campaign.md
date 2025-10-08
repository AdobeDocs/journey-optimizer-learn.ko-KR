---
title: 3과 - 웹 인앱 캠페인 만들기
description: 웹 인앱 캠페인을 만들고 트리거합니다.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
exl-id: 0f84adfb-edb1-47fa-b696-58eec2b33bb1
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 3과 - 웹 인앱 캠페인 만들기

앱에 대한 모바일 경험을 만들었으므로 이 단원에서는 Fréscopa 웹 사이트에서 본 경험 중 하나를 만듭니다. 웹 인앱 캠페인을 만듭니다. 메시지를 디자인하고 사용자 정의하고 메시지를 실행하는 트리거를 정의합니다.

## 학습 목표

* 웹 인앱 캠페인을 만드는 방법을 이해할 수 있습니다.
* 인앱 메시지를 트리거합니다.

## 연습 3.1 웹 인앱 캠페인 만들기

이 연습에서는 캠페인을 만들고 인앱 메시지가 표시되는 웹 페이지를 정의합니다.

1. Journey Optimizer의 왼쪽 탐색에서 **여정 관리**&#x200B;에서 **캠페인**&#x200B;을 선택합니다.

1. **캠페인 만들기**&#x200B;를 클릭합니다.

   ![CreateCampaign](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-create-campaign.png)

1. **캠페인 만들기** 페이지의 **작업** 섹션에서 **인앱 메시지** 확인란을 선택하십시오.

1. **전송 대상** 드롭다운에서 **웹.**&#x200B;을 선택합니다.

1. 다음 URL을 입력하십시오. **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *메시지가 표시될 웹 페이지입니다.*

   ![인앱 URL](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

## 연습 문제 3.2 Campaign 구성

이 페이지에서는 인앱 메시지가 웹 페이지에 표시되도록 트리거하는 캠페인과 이벤트의 속성을 정의합니다. 다른 모든 설정은 기본값으로 둡니다. 이 연습에서는 특정 대상을 정의할 필요가 없습니다.

### 3.2.1 [!UICONTROL 속성 섹션]

1. **속성** 섹션에서 캠페인에 고유한 **이름**&#x200B;을(를) 지정하십시오.

   >[!NOTE]
   > 여러분의 좌석 번호로 이름을 시작하도록 하세요, 그래야 쉽게 할 수 있어요
   > 나중에 캠페인을 찾으십시오.
   > 
   > 예를 들어 좌석 번호가 99인 경우: 
   >
   > ![속성 이름](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 사용자 지정 트리거 규칙 설정

이 섹션에서는 웹 사이트에 메시지가 표시되는 트리거를 정의합니다. 메시지를 자신에게 보낼 수 있는 고유한 트리거를 정의합니다.

1. **[!UICONTROL 트리거 섹션]**&#x200B;까지 아래로 스크롤한 다음 **[!UICONTROL 트리거 편집]**&#x200B;을 클릭합니다.

   ![수정](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. 규칙 빌더에서 **[!UICONTROL 응용 프로그램 실행]**&#x200B;을 클릭하고 드롭다운에서 *플랫폼으로 데이터 보내기*를 선택합니다.
   ![트리거 이벤트 드롭다운](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. **[!UICONTROL + 조건 추가]**&#x200B;를 클릭하여 조건을 추가합니다.

   ![조건 추가 단추](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. **[!UICONTROL 트레이트 선택]** 드롭다운에서 **[!UICONTROL XDM 이벤트 유형]**&#x200B;을 선택합니다.

   ![XDM 이벤트 유형](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. 다음 텍스트 필드에 기억할 수 있는 *`<custom string value>`*&#x200B;을(를) 추가하고 **[!UICONTROL 추가]** `<custom string value>`을(를) 눌러 값을 저장합니다.

   이 사용자 지정 문자열 값은 나중에 메시지를 실행하는 데 사용됩니다.

   >[!TIP]
   > 사용자 지정 문자열 값에 시트 번호를 추가하면 이름이 고유해지고 기억하기 쉬워집니다.
   > 
   > 예: `99web`
   > 

   ![사용자 지정 트리거 문자열 값 추가](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. 오른쪽 상단의 **[!UICONTROL 완료]** 단추를 누릅니다.

>[!SUCCESS]
>
>이제 사용자 지정 트리거 이벤트를 사용하여 웹 인앱 메시지를 정의했습니다.
>
>사용자 지정 트리거가 정의된 ![웹 캠페인](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 인앱 메시지의 콘텐츠 편집

이 섹션에서는 메시지의 내용, 디자인 및 레이아웃을 정의합니다.

1. 작성 구문에 액세스하려면 **작업** 섹션에서 **콘텐츠 편집** 단추를 클릭하십시오.

   ![콘텐츠 편집 단추](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. 작성 프로세스는 위의 모바일 인앱 연습에서 완료한 프로세스와 동일합니다. 자신의 제목, 본문 및 미디어 콘텐츠로 메시지를 자유롭게 편집할 수 있습니다.

   모달 또는 전체 화면 레이아웃을 사용하는 경우 버튼을 추가할 수 있습니다. 다음 URL을 사용하여 제품 페이지를 열 수 있습니다. **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. 메시지 편집이 완료되면 **[!UICONTROL 리뷰를 클릭하여 활성화]**&#x200B;하세요.

1. 검토 화면에서 모든 항목이 정상인 것 같으면 **[!UICONTROL 활성화]**&#x200B;를 클릭하여 웹 인앱 메시지를 게시합니다.

1. Campaign 대시보드로 돌아갑니다.

   4.1.4로 이동하기 전에 캠페인 상태가 **Live**(으)로 변경될 때까지 기다리십시오.

## 연습 3.3 웹 인앱 메시지 트리거

1. Fréscopa 웹 사이트로 이동하여 브라우저의 **연습** 페이지로 이동합니다.

   ![웹 연습 링크](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. 웹 페이지를 새로 고치십시오.

1. 캠페인에 정의한 고유 문자열 값을 입력합니다.

   ![연습 페이지](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-2-exercise-page.png)

1. **[!UICONTROL 보내기]**&#x200B;를 클릭합니다.

>[!SUCCESS]
>
>고유 값으로 전송 단추를 클릭하면 웹 인앱 메시지가 실행됩니다. 웹 인앱 메시지가 화면에 표시되는 것을 볼 수 있습니다.
>
>이 연습에서는 Fréscopa 고객 경험을 통해 본 사용자 지정 XDM 전송 이벤트를 시뮬레이션했습니다.


## 추가 리소스

**비디오 방법:**

* [인앱 캠페인 만들기](/help/channels/create-an-in-app-campaign.md)
* [인앱 메시지 작성](/help/channels/author-in-app-messages.md)

**제품 설명서:**

* [인앱 채널 시작](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [웹 인앱 메시지 만들기](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app-web)
* [인앱 콘텐츠 디자인](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [인앱 알림 확인 및 보내기](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
