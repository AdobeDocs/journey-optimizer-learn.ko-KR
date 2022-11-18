---
title: 이벤트 구성
description: Journey Optimizer 당면 과제를 해결하기 위해 필요한 세 가지 이벤트 구성
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
source-git-commit: 93c5191d9bc0e5cc81d5892251df73251e6c6ea7
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 9%

---


# 이벤트 구성

이 섹션에서는 의 실습 연습에 필요한 세 가지 이벤트를 설정합니다 [Journey Optimizer 과제](/help/challenges/introduction-and-prerequisites.md).

비디오 보기 [이벤트 만들기](/help/set-up-journeys/create-events.md) 를 참조하십시오.

## Luma 온라인 구매 이벤트 만들기

1. 왼쪽 탐색에서 로 이동합니다. [!UICONTROL 관리] 을(를) 선택합니다. *[!UICONTROL 구성]*
1. 에서 [!UICONTROL 대시보드], 선택 *[!UICONTROL 관리*]* 이벤트

![이벤트 관리](assets/create-events.png)

1. 클릭 *[!UICONTROL 이벤트 만들기]*
1. 이벤트 세부 사항 및 매개 변수를 입력합니다.

   | [!UICONTROL 매개 변수] | [!UICONTROL 값] |
   |-------------|-----------|
   | [!UICONTROL 이름] | `LumaOnlinePurchase` |
   | [!UICONTROL 유형] | [!UICONTROL 단일] |
   | [!UICONTROL 이벤트 ID 유형] | [!UICONTROL 규칙 기반] |
   | [!UICONTROL 스키마] | Luma 제품 상호 작용 |
   | [!UICONTROL 필드] | EventType <br>Order.priceTotal<br>purchaseOrderNumber<br>productListItems.quantity<br><b>제품 목록 항목 > Luma 제품 > _*[!DNL yourOrganizationID]* > 제품:</b> <br> 이름<br>가격<br>ProductImageURL<br>제품 URL |

1. 추가 [!UICONTROL 이벤트 ID 조건]: **[!DNL LumaOnlinePurchase.eventType is commerce.purchases]**

   1. 연필 아이콘을 선택하여 필드를 편집합니다
   2. 설정 [!UICONTROL 이벤트 ID 조건 추가] 모달, 드래그 앤 드롭 `eventType` 캔버스에
   3. 선택 `commerce.purchases`
   4. 캔버스에서 확인을 선택합니다
   5. 모달에서 ok 를 선택합니다.

![이벤트 조건 추가](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. 선택 [!UICONTROL 네임스페이스]: `Email(Email)`

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

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

## 만들기 *[!DNL Luma Product Restock] 이벤트

| [!UICONTROL 매개 변수] | [!UICONTROL 값] |
|-------------|-----------|
| [!UICONTROL 이름] | `LumaProductRestock` |
| [!UICONTROL 유형] | [!UICONTROL 비즈니스] |
| [!UICONTROL 스키마] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL 필드] | productID <br> stockEventType<br><b>제품 > Luma 제품 >에서 *[!DNL yourOrganizationID]* > 제품:</b> <br>이름<br>가격<br> ProductImageURL<br>설명 |
| [!UICONTROL 조건] | LumaProductStock입니다._`your organization's ID`.inventoryEvent.stockEventType이 재구성됨 |

## 축하합니다

이제 샌드박스를 사용할 준비가 되었습니다!
