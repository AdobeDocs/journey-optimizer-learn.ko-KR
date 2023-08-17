---
title: 이벤트 구성
description: 실습형 Journey Optimizer 과제에 필요한 세 가지 이벤트 구성
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: df055830da42b94d751890af6c19074ddfea2237
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 100%

---

# 이벤트 구성

이 섹션에서는 [Journey Optimizer 과제](/help/challenges/introduction-and-prerequisites.md) 실습에 필요한 세 가지 이벤트를 설정합니다.

다음 비디오에서 이벤트를 만드는 방법을 설명합니다.

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12&learn=on)

## Luma 온라인 구매 이벤트 만들기

이 이벤트를 사용하면 사용자가 Luma 제품을 온라인으로 구매할 때 Journey Optimizer가 정보를 수신합니다.

1. 다음 매개 변수를 사용하여 이벤트를 만듭니다.

   | [!UICONTROL 매개 변수] | [!UICONTROL 값] |
   |-------------|-----------|
   | [!UICONTROL 이름] | `LumaOnlinePurchase` |
   | [!UICONTROL 유형] | [!UICONTROL 단일] |
   | [!UICONTROL 이벤트 ID 유형] | [!UICONTROL 규칙 기반] |
   | [!UICONTROL 스키마] | `Luma Web Events Schema` |
   | [!UICONTROL 필드] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. 다음과 같이 [!UICONTROL 이벤트 ID 조건]을 추가합니다. `LumaOnlinePurchase.eventType is commerce.purchases`:

   1. 연필 아이콘을 선택하여 필드를 편집합니다.

   1. **[!UICONTROL 이벤트 ID 조건 추가]** 모달에서 `eventType`을 캔버스에 끌어다 놓습니다.
   1. `commerce.purchases`를 선택합니다.
   1. 캔버스에서 **[!UICONTROL 확인]**&#x200B;을 선택합니다.
   1. 모달에서 **[!UICONTROL 확인]**&#x200B;을 선택합니다.

   ![이벤트 조건 추가](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. 다음 [!UICONTROL 네임스페이스]를 선택합니다. `Luma CRM ID (lumaCrmId)`

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## *[!DNL Luma Product Restock]* 이벤트 만들기

| [!UICONTROL 매개 변수] | [!UICONTROL 값] |
|-------------|-----------|
| [!UICONTROL 이름] | `LumaProductRestock` |
| [!UICONTROL 유형] | [!UICONTROL 비즈니스] |
| [!UICONTROL 스키마] | [!DNL Luma Product Inventory Event Schema] |
| [!UICONTROL 필드] | SKU <br> stockEventType<br><b>LumaProductCatalogSchema._yourOrganizationID.product :</b> <br>name<br>price<br> ImageURL<br>description |
| [!UICONTROL 조건] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType is restock |

축하합니다! 이제 샌드박스를 사용할 준비가 되었습니다.
