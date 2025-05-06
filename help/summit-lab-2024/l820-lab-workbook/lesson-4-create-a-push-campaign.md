---
title: 4과 - 푸시 캠페인 만들기
description: 프로필 데이터를 검토하고 Journey Optimizer에서 푸시 알림을 만들어 대상자에게 보내는 방법을 알아봅니다.
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
source-git-commit: b5577da9a983594cb34edf5c53e2995024e30e78
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 2%

---

# 4과 - 푸시 캠페인 만들기

이전 연습에서는 커피 마니아인 Fréscopa 고객이었습니다. 당신은 그들의 웹 사이트 및 Fréscopa 앱을 통해 브랜드와 상호 작용하고 많은 트랜잭션 메시지를 받았습니다. 이러한 메시지는 웹 사이트 또는 애플리케이션과 사용자의 상호 작용을 통해 트리거됩니다.

이 연습에서는 마케터의 역할을 맡은 것으로 가정하고 Frésopa를 위한 마케팅 캠페인을 구현합니다. 이 캠페인은 푸시 채널을 활용하여 Fréscopa 앱 사용자를 타깃팅합니다. 푸시 알림은 앱을 사용하지 않는 경우에도 앱 사용자에게 알림을 보내는 데 사용되지만, 앱을 사용하여 사용자를 다시 참여시키는 데에도 사용됩니다. 목표는 10% 할인을 제공하여 고객이 하우스 블렌드를 구입하도록 유도하는 것입니다.

## 학습 목표

* 푸시 캠페인을 만드는 방법을 이해할 수 있습니다.
* 푸시 메시지를 디자인하는 방법을 이해합니다.

<br>

## 연습 4.1 - 푸시 캠페인 만들기

이 연습에서는 푸시 캠페인을 만들고, 푸시 알림을 디자인하고, 사용자 지정하고, 푸시 알림을 사용자 지정 장치로 보냅니다.

1. Journey Optimizer의 왼쪽 탐색 영역에서 **[!UICONTROL 여정 관리]** 섹션에서 **캠페인**&#x200B;을 선택합니다.

1. **[!UICONTROL 캠페인 만들기]**&#x200B;를 클릭합니다.

   ![캠페인 만들기](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. **[!UICONTROL 캠페인 만들기]** 페이지의 **[!UICONTROL 작업]** 섹션에서 **[!UICONTROL 푸시 알림]** 확인란을 선택하십시오.

1. **[!UICONTROL 앱 표면]** 드롭다운에서 *[!DNL Frecopa-Push]*&#x200B;을(를) 선택합니다.

1. 푸시 캠페인을 만들려면 **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

   ![앱 표면](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>이제 Campaign 속성 페이지에 있어야 합니다.
> ![캠페인 속성](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## 연습 4.2 - 캠페인 구성

이 페이지에서는 캠페인의 속성, 대상자, 작업 및 일정을 구성합니다.

### 4.2.1 [!UICONTROL 속성 섹션]

캠페인의 이름을 지정하십시오. 이름을 좌석 번호로 시작해야 검색 시 캠페인을 쉽게 찾을 수 있습니다.

예를 들어 시트 번호가 99이면 `99 - 10% Discount Campaign`입니다.

### 4.2.2 **[!UICONTROL 대상 섹션]**

1. 대상 섹션에서 **[!UICONTROL 대상 선택]**&#x200B;을 클릭합니다.

   ![대상 섹션](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. **[!UICONTROL 대상자 선택]** 화면에서 대상자를 검색합니다.

   **랩 - 시트`your seat number`**

1. 대상을 선택한 다음 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

   ![대상자 선택](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 푸시 알림의 콘텐츠 편집

이 연습에서는 푸시 알림을 디자인하고 사용자 지정합니다.

1. **[!UICONTROL 작업]** 섹션에서 **[!UICONTROL 콘텐츠 편집] 단추**&#x200B;를 클릭합니다.

   ![콘텐츠 편집 단추](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. 다음 화면에서는 보유한 모바일 장치에 따라 [!DNL iOS™] 또는 [!DNL Android™] 탭을 선택하여 콘텐츠를 구성합니다.

>[!BEGINTABS]

>[!TAB iOS]

![iOS 탭](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Android 탭](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL 메시지 작성] 섹션

1. **메시지 작성:** 원하는 텍스트를 자유롭게 추가하십시오. 다음은 사용할 수 있는 예입니다.

   * 제목: `Get 10% off today!`
   * 본문: `Today only! Get 10% off on your House Blend coffee purchase!`

     ![메시지 작성](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 메시지의 클릭 시 동작을 **제품 페이지 열기**(으)로 변경

1. **[!UICONTROL 클릭 동작]** 섹션의 **[!UICONTROL 본문 클릭 동작]** 드롭다운에서 **[!UICONTROL 딥링크]**&#x200B;를 선택합니다.

1. 다음 URL을 복사하여 **URL 필드**&#x200B;에 붙여 넣으십시오.

   `dxdemo://exoticVibes`

   ![딥링크](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 메시지에 이미지 추가

1. **[!UICONTROL 미디어 추가]** 섹션에서 **[!UICONTROL 미디어 추가]**&#x200B;를 클릭합니다.

   ![미디어 단추 추가](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. **[!UICONTROL Assets 선택]** 화면의 왼쪽 탐색에서 **Fréscopa 폴더**&#x200B;를 열고 해당 폴더에서 이미지를 선택합니다.

   예: `HouseBlend.png`

1. 이미지를 클릭하고 **[!UICONTROL 선택] 단추**&#x200B;를 클릭하여 푸시 알림에 이미지를 추가합니다.

   ![이미지 선택](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. 미리 보기 화면에서 **[!UICONTROL 보기 확장]**&#x200B;을 클릭합니다.
   > 1. 메시지를 미리 봅니다.
   > <br>
   >
   > ![보기 확장](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

### 보너스 운동

이 부분의 연습을 완료했지만 시간이 남아 있다면 보너스 운동을 시도해 보십시오.

+++ 보너스 운동

#### 수신자의 이름을 추가하여 보내는 메시지 개인화

1. **[!UICONTROL 본문]** 필드 옆에 있는 **개인화 대화 상자**&#x200B;를 클릭합니다.

   ![개인화 단추](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-button.png)

1. **개인화 대화 상자** 화면에서 텍스트의 이름을 추가할 위치에 커서를 놓습니다.

1. 왼쪽 탐색에서 **프로필 특성**&#x200B;이 선택되어 있는지 확인하십시오.

   ![프로필 특성](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. **검색 필드**&#x200B;에서 `first name`을(를) 검색합니다.

1. **이름(프로필 특성>사용자>전체 이름)** 옆에 있는 **+**&#x200B;을 클릭하여 텍스트에 개인화 필드를 추가합니다.

   ![이름 검색](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > 텍스트는 다음과 같아야 합니다.
   > 
   >![Personalization 토큰](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-token.png)

1. 개인화를 저장하려면 **[!UICONTROL 저장]**&#x200B;을 클릭하세요.


   >[!SUCCESS]
   >
   > 1. 미리 보기 화면에서 **[!UICONTROL 보기 확장]**&#x200B;을 클릭합니다.
   > 1. 메시지를 미리 봅니다.
   > 
   > ![보기 확장](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. 검토 및 활성화

메시지의 내용에 만족하면 메시지를 활성화할 수 있습니다.

1. 활성화하려면 **[!UICONTROL 검토]**&#x200B;를 클릭하세요.

   ![검토 및 활성화 단추](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. **[!UICONTROL 활성화 검토]** 화면에서 **[!UICONTROL 활성화]**&#x200B;를 클릭합니다.

   ![화면을 활성화하기 위한 검토](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> **캠페인 개요 페이지**&#x200B;에서 캠페인을 찾아 상태를 확인하세요.
>
> ![캠페인 상태](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> 상태가 처리에서 라이브, 완료로 변경됩니다. 이 작업은 2분 정도 걸릴 수 있습니다.
> 상태가 완료됨으로 변경된 후:
>
> ![푸시 결과](/help/summit-lab-2024/l820-lab-workbook/assets/2-3-push-notification-result.png)

## 추가 리소스

**비디오 방법:**

* [푸시 캠페인 구성 및 보내기](/help/channels/create-a-push-campaign.md)

**제품 설명서:**

* [푸시 알림 시작](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/push/get-started-push)
* [푸시 알림 만들기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/push/create-push)
* [푸시 알림 디자인](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/push/design-push)
* [푸시 알림 확인 및 보내기](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/push/send-push)
