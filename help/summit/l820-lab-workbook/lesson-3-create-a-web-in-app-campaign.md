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
source-git-commit: c509c768d07984d07ed2ec65634e000c54bb6ff1
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---



# 3과 - 웹 인앱 캠페인 만들기

앱에 대한 모바일 경험을 만들었으므로 이 단원에서는 Fréscopa 웹 사이트에서 본 경험 중 하나를 만듭니다. 웹 인앱 캠페인을 만듭니다. 메시지를 디자인하고 사용자 정의하고 메시지를 실행하는 트리거를 정의합니다.

## 학습 목표

* 웹 인앱 캠페인을 만드는 방법을 이해할 수 있습니다.
* 인앱 메시지를 트리거합니다.

## 연습 3.1 웹 인앱 캠페인 만들기

이 연습에서는 캠페인을 만들고 인앱 메시지가 표시되는 웹 페이지를 정의합니다.

1. Journey Optimizer의 왼쪽 탐색 메뉴에서 **여정 관리** 선택 **캠페인**.

1. 클릭 **캠페인 만들기**.

   ![캠페인 만들기](/help/summit/l820-lab-workbook/assets/4-1-create-campaign.png)

1. 다음에서 **캠페인 만들기** 페이지, **작업** 섹션에서 **인앱 메시지** 확인란.

1. 다음에서 **전송 대상** 드롭다운, 선택 **웹.**

1. 다음 URL을 입력합니다. **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *메시지가 표시될 웹 페이지입니다.*

   ![인앱 URL](/help/summit/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

## 연습 문제 3.2 Campaign 구성

이 페이지에서는 인앱 메시지가 웹 페이지에 표시되도록 트리거하는 캠페인과 이벤트의 속성을 정의합니다. 다른 모든 설정은 기본값으로 둡니다. 이 연습에서는 특정 대상을 정의할 필요가 없습니다.

### 3.2.1 [!UICONTROL 속성 섹션]

1. 다음에서 **속성** 섹션, 캠페인에 고유한 이름을 지정하십시오. **이름**:

   >[!NOTE]
   > 여러분의 좌석 번호로 이름을 시작하도록 하세요, 그래야 쉽게 할 수 있어요
   > 나중에 캠페인을 찾으십시오.
   > 
   > 예를 들어 좌석 번호가 99인 경우: 
   >
   > ![속성 이름](/help/summit/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 사용자 지정 트리거 규칙 설정

이 섹션에서는 웹 사이트에 메시지가 표시되는 트리거를 정의합니다. 메시지를 자신에게 보낼 수 있는 고유한 트리거를 정의합니다.

1. 아래로 스크롤하여 **[!UICONTROL 트리거 섹션]**&#x200B;을 클릭한 다음 을 클릭합니다 **[!UICONTROL 트리거 편집]**.

   ![수정](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. 규칙 빌더에서 를 클릭합니다. **[!UICONTROL 애플리케이션 실행]** 드롭다운에서 을 선택합니다.  *플랫폼으로 데이터 전송됨*.
   ![트리거 이벤트 드롭다운](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. 다음을 클릭하여 조건 추가 **[!UICONTROL + 조건 추가]**.

   ![조건 추가 단추](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. 다음에서 **[!UICONTROL 트레이트 선택]** 드롭다운, 선택 **[!UICONTROL XDM 이벤트 유형]**.

   ![XDM 이벤트 유형](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. 다음 텍스트 필드에 *`<custom string value>`* 다음을 기억하고 **[!UICONTROL 추가]** `<custom string value>` 값을 저장합니다.

   이 사용자 지정 문자열 값은 나중에 메시지를 실행하는 데 사용됩니다.

   >[!TIP]
   > 사용자 지정 문자열 값에 시트 번호를 추가하면 이름이 고유해지고 기억하기 쉬워집니다.
   > 
   > 예: `99web`
   > 

   ![사용자 지정 트리거 문자열 값 추가](/help/summit/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. 누르기 **[!UICONTROL 완료]** 오른쪽 상단의 버튼입니다.

>[!SUCCESS]
>
>이제 사용자 지정 트리거 이벤트를 사용하여 웹 인앱 메시지를 정의했습니다.
>
>![사용자 지정 트리거가 정의된 웹 캠페인](/help/summit/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 인앱 메시지의 콘텐츠 편집

이 섹션에서는 메시지의 내용, 디자인 및 레이아웃을 정의합니다.

1. 다음을 클릭합니다. **콘텐츠 편집** 의 단추 **작업** 섹션에 액세스할 수 있습니다.

   ![콘텐츠 편집 단추](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. 작성 프로세스는 위의 모바일 인앱 연습에서 완료한 프로세스와 동일합니다. 자신의 제목, 본문 및 미디어 콘텐츠로 메시지를 자유롭게 편집할 수 있습니다.

   모달 또는 전체 화면 레이아웃을 사용하는 경우 버튼을 추가할 수 있습니다. 다음 URL을 사용하여 제품 페이지를 열 수 있습니다. **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. 메시지 편집이 끝나면 **[!UICONTROL 활성화하려면 검토]**.

1. 검토 화면에서 모든 것이 잘 보이는 경우 **[!UICONTROL 활성화]** 을 클릭하여 웹 인앱 메시지를 게시합니다.

1. Campaign 대시보드로 돌아갑니다.

   캠페인 상태가 변경될 때까지 대기 **라이브** 4.1.4로 이동하기 전에

## 연습 3.3 웹 인앱 메시지 트리거

1. Fréscopa 웹 사이트로 이동하여 **운동** 브라우저에 페이지를 표시합니다.

   ![웹 연습 링크](/help/summit/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. 웹 페이지를 새로 고치십시오.

1. 캠페인에 정의한 고유 문자열 값을 입력합니다.

   ![연습 페이지](/help/summit/l820-lab-workbook/assets/4-2-exercise-page.png)

1. **[!UICONTROL 보내기]**&#x200B;를 클릭합니다.

>[!SUCCESS]
>
>고유 값으로 전송 단추를 클릭하면 웹 인앱 메시지가 실행됩니다. 웹 인앱 메시지가 화면에 표시되는 것을 볼 수 있습니다.
>
>이 연습에서는 Fréscopa 고객 경험을 통해 본 사용자 지정 XDM 전송 이벤트를 시뮬레이션했습니다.
