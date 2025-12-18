---
title: 단원 2 - 모바일 인앱 캠페인 만들기
description: 모바일 인앱 캠페인을 만들고 트리거합니다.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
exl-id: fe18eca7-229c-4867-ab34-1862bad63124
source-git-commit: 7b3d668e8400d9f86c764f5dc4c4455b50cd0cdc
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 1%

---

# 단원 2 - 모바일 인앱 캠페인 만들기

이 단원에서는 모바일 인앱 메시지를 만들고 트리거합니다.

## 학습 목표

* 인앱 메시지가 트리거되는 방법을 이해합니다.
* 모바일 인앱 캠페인을 만드는 방법을 이해할 수 있습니다.
* 인앱 메시지를 트리거합니다.

## 연습 문제 2.1 - Journey Optimizer에 로그인

1. [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"} 열기
2. 다음 세부 정보를 사용하여 로그인합니다.
   <br>
   **사용자 이름:** L820+**`<your seat number>`**@adobeeventlab.com
   **암호:**   Adobe2024!
   <br>
로그인에 대한 자세한 내용은 랩 컴퓨터 바탕 화면에서 확인할 수 있습니다. Adobe ID 및 암호를 사용합니다.
   ![데스크톱](/help/summit-lab-2024/l820-lab-workbook/assets/desk-top.png)

   ![로그인 화면](/help/summit-lab-2024/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. 다음 두 화면을 건너뛸 수 있습니다.
   <br>
   ![전화 번호](/help/summit-lab-2024/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![Personalization 팝업](/help/summit-lab-2024/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Journey Optimizer 및 홈 페이지에 로그인해야 합니다.
>
>![AJO 홈 페이지](/help/summit-lab-2024/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## 연습 2.2 모바일 인앱 캠페인 만들기

이 연습에서는 앱을 열 때 트리거되는 인앱 메시지 캠페인을 만듭니다.

1. Journey Optimizer의 왼쪽 탐색에서 **[!UICONTROL 캠페인]**&#x200B;을 선택합니다.

1. **[!UICONTROL 캠페인 만들기]**&#x200B;를 클릭합니다.

   ![캠페인 만들기](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. **[!UICONTROL 캠페인 만들기]** 페이지의 **[!UICONTROL 작업]** 섹션에서 **[!UICONTROL 인앱 메시지]** 확인란을 선택하십시오.

1. **[!UICONTROL 전송 대상]** 드롭다운에서 **[!DNL Mobile]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL 앱 표면]** 드롭다운에서 **[!DNL Frecopa Mobile App]**&#x200B;을(를) 선택합니다.

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

   ![앱 표면](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>이제 Campaign 속성에 있어야 합니다.
>
> ![캠페인 속성](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## 연습 2.3 캠페인 구성

### 2.3.1 [!UICONTROL 속성 섹션]

캠페인의 이름을 지정하십시오. 캠페인이 다시 쉽게 찾을 수 있도록 좌석 번호로 이름을 시작해야 합니다.

예를 들어 시트 번호가 99이면 `99 - Welcome Campaign`입니다.

![속성 섹션](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 사용자 지정 트리거 규칙 설정

1. **[!UICONTROL 트리거 섹션]**&#x200B;까지 아래로 스크롤한 다음 **[!UICONTROL 트리거 편집]**&#x200B;을 클릭합니다.

   ![수정](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. 규칙 빌더에서 **[!UICONTROL 응용 프로그램 실행]**&#x200B;을 클릭하고 드롭다운에서 *플랫폼으로 데이터 보내기*를 선택합니다.
   ![데이터 플랫폼으로 전송됨](/help/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. **[!UICONTROL 조건 추가]**&#x200B;를 클릭하여 조건을 추가합니다.

   ![조건 추가 단추](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. **[!UICONTROL 트레이트 선택]** 드롭다운에서 **[!UICONTROL XDM 이벤트 유형]**&#x200B;을 선택합니다.

   ![XDM 이벤트 유형](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. 다음 텍스트 필드에 기억할 수 있는 *`<custom string value>`*&#x200B;을(를) 추가합니다.

1. 값을 저장하려면 **[!UICONTROL 추가**] `<custom string value>`를 클릭합니다.

   이 사용자 지정 문자열 값은 나중에 메시지를 실행하는 데 사용됩니다.

   >[!TIP]
   > 사용자 지정 문자열 값에 시트 번호를 추가하면 고유하고 기억하기 쉬워집니다.
   > 
   > 예: `99exerciseTrigger`

   ![사용자 지정 트리거 문자열 값 추가](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. 오른쪽 상단의 **[!UICONTROL 완료]**&#x200B;를 클릭합니다.

>[!SUCCESS]
>
>이제 사용자 지정 트리거 이벤트를 사용하여 인앱 메시지를 정의했습니다.
>
>사용자 지정 트리거가 정의된 ![캠페인](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 인앱 메시지의 콘텐츠 편집

**[!UICONTROL 작업]** 섹션에서 **[!UICONTROL 콘텐츠 편집]**&#x200B;을 클릭합니다.

![콘텐츠 편집 단추](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

인앱 메시지 콘텐츠를 구성할 수 있는 [!UICONTROL 인앱 메시지] 편집기가 표시됩니다.

#### 2.3.3.1 레이아웃

메시지에 적용할 레이아웃을 선택하십시오.

예를 들어 **[!UICONTROL 모달]**&#x200B;을 클릭하여 인앱 메시지를 모달 레이아웃으로 만듭니다.

![모달 단추](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 메시지 작성 및 캠페인 게시

1. 미디어 섹션에서 다음 URL에 붙여 넣습니다. `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
값 필드 바깥쪽을 클릭하면 이미지가 표시됩니다.

   미리 보기에 ![미디어가 표시됨](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-media.png)

2. 다음 **[!UICONTROL 콘텐츠]** 섹션에서 **[!UICONTROL 헤더]** 및 **[!UICONTROL 본문]**&#x200B;에 대한 메시지에 표시할 사용자 지정 텍스트를 추가합니다.

   ![머리글 및 본문](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-content.png)

3. 추가 옵션:
   1. **단추:**

      ![단추 섹션](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. 편집기의 이 섹션에서는 단추 텍스트 필드를 편집하여 CTA 단추의 텍스트를 사용자 정의할 수 있습니다.

      2. **[!UICONTROL Interact event]** 필드는 사용자가 CTA을 누를 때 SDK에 전달되는 값을 정의하는 데 사용됩니다.

      3. **[!UICONTROL Target]** 필드는 CTA에서 사용자를 가져올 위치를 정의하는 데 사용됩니다. 여기에는 URL 및 딥링크가 포함됩니다. 예를 들어 `dxdemo://exoticVibes`과(와) 같은 제품 페이지에 이 딥링크를 추가할 수 있습니다.

      4. **[!UICONTROL + 추가 단추]**&#x200B;를 눌러 단추를 추가할 수 있습니다.

      5. 메시지에 두 번째 버튼이 추가되면 드롭다운 상자로 버튼 레이아웃을 변경할 수 있습니다.


   2. **고급 서식**

      ![고급 서식 설정 전환](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      이 토글을 활성화하면 편집기에 추가 사용자 지정 옵션이 제공됩니다.

      1. 미디어 크기
      1. 글꼴
      1. Pt 크기
      1. 글꼴 색상
      1. 정렬

      ![고급 서식 옵션](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **설정 탭**

      이 탭으로 전환하고 **[!UICONTROL 미리 보기]** 섹션에서 **앱 미리 보기**&#x200B;를 변경할 수 있습니다.
      <br>\
      ![설정 탭](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. **[!UICONTROL 레이아웃]** 섹션은 이미지를 배경색 또는 단색으로 사용할 수 있는 옵션을 제공합니다.

      2. **[!UICONTROL 메시지]** 섹션에서 메시지에 사용할 수 있는 사용자 지정 상호 작용을 제공합니다.
         1. 사용자 지정 제스처
         2. UI 인계
         3. 사용자 정의 UI 인계
         4. 사용자 정의 크기
         5. 사용자 지정 위치
         6. 사용자 지정 애니메이션
         7. 메시지 라운드 모서리
   <br>
4. 콘텐츠 작성이 완료되고 메시지에 만족하면 **[!UICONTROL 활성화 검토] 단추를 클릭하세요**.

   >[!SUCCESS]
   >
   > 이제 모바일 인앱 메시지 작성을 완료했습니다. 이제 Campaign **[!UICONTROL 활성화 검토]** 페이지에 있어야 합니다.
   >
   >![검토 및 활성화](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > 여기에서 메시지의 전체 요약을 볼 수 있습니다.
   >
   > *규칙을 트리거할 때 사용한 사용자 지정 값을 기록해 두십시오. 이 값은 인앱 메시지를 실행하는 데 사용됩니다. 사용된 값은 요약 페이지의 강조 표시 영역에서 찾을 수 있습니다.*

   >[!NOTE]
   >인앱 메시지의 현재 트리거는 기본 **응용 프로그램 시작 이벤트 발생**&#x200B;입니다. 즉, 앱이 시작될 때 인앱 메시지가 트리거됩니다. **[!UICONTROL 일정 섹션]**&#x200B;에서 볼 수 있습니다.

5. Campaign을 모두 검토한 경우 활성화 버튼을 눌러 Campaign을 게시합니다.
   <br>
   ![활성화](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> 이제 캠페인 대시보드가 표시됩니다. 스크롤하거나 검색 기능을 사용하여 캠페인을 찾습니다. Campaign에서 상태를 **[!UICONTROL Live]**(~1분)로 변경하면 Campaign이 게시됩니다.
>
> ![게시된 캠페인](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## 연습 2.4 모바일 인앱 메시지 트리거

페이로드를 새로 고치고 새로 게시된 캠페인을 다운로드하려면 다음을 수행하십시오.

1. 모바일 장치에서 Fréscopa 앱을 완전히 닫습니다.
2. Fréscopa 앱을 다시 엽니다.
3. 이제 앱의 연습 탭으로 이동합니다.

   ![연습 단추](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. 텍스트 필드에 Campaign에서 정의한 사용자 지정 트리거 값을 입력합니다. 그런 다음 제출을 누릅니다.


   ![수정](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>제출을 클릭하면 트리거가 수동으로 실행되며 작성한 인앱 알림이 팝업됩니다.
>
>![인앱 메시지](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *메시지를 트리거하는 데 문제가 있는 경우 다음을 확인하십시오.*
> 
> * *모바일 앱의 이벤트 이름 필드에 트리거 규칙 값을 캠페인에 사용한 것과 정확히 동일하게 입력해야 합니다.*
> * *대소문자가 올바른지, 선행 또는 끝 공백이 없는지 확인하십시오.*
> * *Campaign 대시보드에서 캠페인을 다시 클릭하여 Campaign 검토 페이지로 돌아가면 사용한 트리거 규칙 값을 조회할 수 있습니다.*

방금 첫 번째 Journey Optimizer 인앱 메시지를 작성 및 게시했습니다!


## 보너스 연습: 중복 캠페인 및 장치에서 미리 보기

**캠페인 복제** 및 **장치에서 미리 보기** 기능은 기본 기능으로, 캠페인을 복제하고 인앱 메시지를 활성화하기 전에 장치에서 직접 테스트하고 검토할 수 있습니다. 이 연습에서는 이 기능을 사용하고 연습 3.1에서 만든 메시지를 미리 보는 방법을 알아봅니다.

1. 캠페인 대시보드 페이지에서 캠페인 이름을 클릭하여 방금 만든 캠페인을 열고 캠페인을 엽니다. **[!UICONTROL 캠페인 검토]** 페이지로 돌아갑니다.
1. **[!UICONTROL 복제 단추]**&#x200B;를 누릅니다. 이렇게 하면 복제되는 새 캠페인의 이름을 지정하는 새 프롬프트가 열립니다. **[!DNL _copy]**&#x200B;이(가) 기본적으로 추가되는 기본 이름을 쉽게 기억하거나 사용하는 새 이름을 추가합니다.

   ![캠페인 복제](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. 복제 버튼을 누르면 중복 캠페인이 만들어지고 캠페인 대시보드로 돌아갑니다.
1. 캠페인이 복제되면 새 캠페인을 엽니다.

1. **[!UICONTROL 캠페인 검토]** 페이지 또는 **[!UICONTROL 캠페인 작성자]** 단계에서 디바이스에서 미리 보기 기능에 액세스할 수 있습니다.

   ![장치 미리 보기 단추](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. 다음으로 장치에 연결 화면에서 **[!UICONTROL 시작 단추]**&#x200B;를 클릭합니다.

   ![시작 단추](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Fréscopa 앱을 시작하도록 구성된 기본 URL을 입력하십시오. `dxdemo://`

   ![미리 보기 url](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. 화면의 지침을 따릅니다.
   1. 모바일 기기로 QR 코드를 스캔하면 Fréscopa 앱이 열리고 화면에 표시된 핀을 입력할 수 있습니다.
   2. 장치의 Assurance 화면에서 AJO에 표시된 핀을 입력하고 핀을 입력한 후 오른쪽 하단에 나타나는 연결 버튼을 클릭합니다.


   ![pin 입력](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. 이 팝업은 컴퓨터 화면에 표시됩니다

   ![팝업](/help/summit-lab-2024/l820-lab-workbook/assets/3-3-pop-up.png)

1. 완료(Done) 단추를 누릅니다. 이렇게 하면 대화 상자가 닫히고 휴대폰이 이제 장치의 미리 보기에 연결됩니다.


>[!SUCCESS]
>
> 인앱 메시지가 장치에 표시됩니다.
>
> *연결되면 인앱 메시지가 표시될 때마다 **[!UICONTROL 장치에서 미리 보기] 단추를 클릭합니다**.

## 추가 리소스

**비디오 방법:**

* [인앱 캠페인 만들기](/help/channels/create-an-in-app-campaign.md)
* [인앱 메시지 작성](/help/channels/author-in-app-messages.md)

**제품 설명서:**

* [인앱 채널 시작](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/in-app/get-started-in-app)
* [모바일 인앱 메시지 만들기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/in-app/create-in-app)
* [인앱 콘텐츠 디자인](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/in-app/design-in-app)
* [인앱 알림 확인 및 보내기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/in-app/send-in-app)
