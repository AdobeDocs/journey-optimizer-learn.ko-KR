---
title: 이벤트 구성
description: 실습 위주의 Journey Optimizer 과제에 필요한 세 가지 이벤트 구성
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 7ecbed1b722d7f05ffd4a7c7071358d993cb1392
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 10%

---

# 이벤트 구성

이 섹션에서는 의 실습 연습에 필요한 세 가지 이벤트를 설정합니다 [Journey Optimizer 과제](/help/challenges/introduction-and-prerequisites.md).

다음 비디오에서는 이벤트를 만드는 방법을 설명합니다.

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12)

## Luma 온라인 구매 이벤트 만들기

이 이벤트를 사용하는 경우 Journey Optimizer은 한 사람이 온라인으로 luma 제품을 구매할 때 정보를 받습니다.

1. 다음 매개 변수로 이벤트를 만듭니다.

   | [!UICONTROL 매개 변수] | [!UICONTROL 값] |
   |-------------|-----------|
   | [!UICONTROL 이름] | `LumaOnlinePurchase` |
   | [!UICONTROL 유형] | [!UICONTROL 단일] |
   | [!UICONTROL 이벤트 ID 유형] | [!UICONTROL 규칙 기반] |
   | [!UICONTROL 스키마] | `Luma Web Events Schema` |
   | [!UICONTROL 필드] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

2. 추가 [!UICONTROL 이벤트 ID 조건]: `LumaOnlinePurchase.eventType is commerce.purchases`

   1. 연필 아이콘을 선택하여 필드를 편집합니다
   2. 설정 [!UICONTROL 이벤트 ID 조건 추가] 모달, 드래그 앤 드롭 `eventType` 캔버스에
   3. 선택 `commerce.purchases`
   4. 캔버스에서 확인을 선택합니다
   5. 모달에서 ok 를 선택합니다.

![이벤트 조건 추가](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. 선택 [!UICONTROL 네임스페이스]: `Luma CRM ID (lumaCrmId)`

2. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 만들기 *[!DNL Luma Wishlist Add]* 이벤트

| [!UICONTROL 매개 변수] | [!UICONTROL 값] |
|-------------|-----------|
| [!UICONTROL 이름] | `LumaWishlistAdd` |
| [!UICONTROL 유형] | [!UICONTROL 단일] |
| [!UICONTROL 이벤트 ID 유형] | [!UICONTROL 규칙 기반] |
| [!UICONTROL 스키마] | `Luma Product Interactions` |
| [!UICONTROL 필드] | EventType<br>productListItem.quantity<br><b>제품 목록 항목 > Luma 제품 > _*[!DNL yourOrganizationID]* > 제품:</b> <br>이름<br>가격<br> ProductImageURL<br>제품 URL |
| [!UICONTROL 조건] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL 네임스페이스] | 이메일(EMail) |

## 만들기 *[!DNL Luma Product Restock]* 이벤트

| [!UICONTROL 매개 변수] | [!UICONTROL 값] |
|-------------|-----------|
| [!UICONTROL 이름] | `LumaProductRestock` |
| [!UICONTROL 유형] | [!UICONTROL 비즈니스] |
| [!UICONTROL 스키마] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL 필드] | SKU <br> stockEventType<br><b> yourOrganizationID > product:</b> <br>이름<br>가격<br> ImageURL<br>설명 |
| [!UICONTROL 조건] | LumaProductStock입니다._`your organization's ID`.inventoryEvent.stockEventType이 재구성됨 |

## 축하합니다

이제 샌드박스를 사용할 준비가 되었습니다!
