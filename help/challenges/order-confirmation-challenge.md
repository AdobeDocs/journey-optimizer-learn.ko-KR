---
title: 주문 확인 이메일 만들기
description: 트랜잭션 메시지를 만들고 개인화하는 방법에 대한 지식을 테스트합니다..
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 6737f81f9cd9fc34740ce60e10c8036e29f97f68
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 93%

---


# 주문 확인 이메일 만들기

![주문 확인](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 과제 | 주문 확인 트랜잭션 이메일 만들기 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[메시지 편집기로 이메일 콘텐츠 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/create-content-with-the-email-designer.html?lang=ko)</li> <li>[개인화에 컨텍스트 기반 이벤트 정보 사용](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=ko)</li><li>[개인화에 도우미 기능 사용](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=ko)</li></ul> |
| 다운로드할 자산 | [주문 확인 자산](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

{style=&quot;table-layout:auto&quot;}

## 스토리

Luma는 온라인 스토어를 시작하고 고객 경험을 향상하고자 합니다. 고객이 주문을 하면 주문 확인 이메일을 제공합니다.

## 과제

Luma 고객이 온라인 주문을 완료하면 주문 확인 이메일을 보내는 여정을 만듭니다.

>[!BEGINTABS]

>[!TAB 작업]

1. `Luma - Order Confirmation`(이)라는 여정을 만듭니다.

1. 이벤트 사용: `LumaOnlinePurchase`.

1. 만들기 **트랜잭션**  이메일 호출됨 `Luma - Order Confirmation`.

   * 제목 &quot;`FirstName` 님, 구매해 주셔서 감사합니다&quot;

   * `Luma - Order summary` 템플릿을 사용하고 수정하십시오.

      * `You may also like` 섹션 제거

      * 이메일 아래쪽에 구독 취소 링크 추가

이메일을 다음과 같이 구조화해야 합니다.
<table>
<tr>
<td>
  <div>
     <strong> 헤더 섹션</strong>
      </div>
  </td>
  <td>
      <p>
     <li>luma_logo.png</li>
    <li>링크를 통해 Luma 웹 사이트(https://.adobedemo.com/content/luma/us/en.html)로 연결되어야 함</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>주문 확인 섹션
    </strong>
  </td>
  <td>
    <p>
    <strong>텍스트</strong><p>
    <em>{firstName} 님, 안녕하세요.</em><p>
   <div>
    <p>
     <em>주문이 완료되었습니다.
    <p>제품이 배송되면 주문을 추적할 수 있도록 추적 번호가 포함된 이메일을 보냅니다.</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong> 배송처 섹션</strong>
      </div>
      <p>
      <li>이름과 성은 프로필에서 가져온 것입니다.
      <li>템플릿의 하드 코딩된 주소를 <b>배송 주소</b>로 바꾸기
      <li>주소 세부 사항은 이벤트의 컨텍스트 속성(거리 1, 도시, 우편 번호, 주)
      <li> <i>할인, 총액, 도착</i> 제거</p>
  </td>
  <td>
  <p> 배송처:</p>
      <em>{firstName} {lastName}<br>
     {Street 1}<br>
     {City}, {State} {postalCode}<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>주문 세부 사항 섹션</strong>
      </div>
       <p><li><b>배송지</b> 섹션 아래에 이 섹션 추가
      </p><br>
      <p><b>팁:</b>
      <li>이 섹션에 <b>1:2열 왼쪽</b> 구조 구성 요소 사용
      <li>컨텍스트 기반 이벤트 정보입니다.
      <li>[!UICONTROL helper function] 사용: [!UICONTROL Each]
      <li>코드 편집기 형식으로 전환하여 컨텍스트 데이터를 추가합니다.
  </td>
  <td>
    <strong>Header</strong>
    <p>
  주문: <em>{purchaseOrderNumber}</em>
    </p>
    <strong>주문 제품 목록:
  </strong>
  <p>각 제품 목록에 이미지, 가격, 이름을 포함하여 이 순서로 표시합니다.
  <p>성공한 경우 각 품목의 레이아웃 모습:
 <img alt="주문" src="./assets/c2-order.png"> 
<p><b>장바구니에 링크 추가</b>
<p>URL의 주문 ID를 구매 주문 번호로 바꾸기:
   <i>https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId=90845952-c2ea-4872-8466-5289183e4607</i>
</td>
  </tr>
</table>

>[!TIP]
>
>여정의 문제를 해결하는 가장 좋은 방법은 시간 제한이나 오류가 발생할 경우 모든 메시지 작업에 대체 경로를 추가하는 것입니다.

>[!TAB 성공 기준]

만든 [여정]을 테스트 모드에서 트리거하고 자신에게 이메일을 보냅니다.

1. 테스트 모드로 전환하기 전에 테스트 이메일을 자신의 이메일 주소로 보낼 수 있도록 이메일 매개 변수를 재정의합니다.
   1. 이메일 세부 사항 보기를 엽니다.
   1. [이메일 매개 변수] 섹션에서 T 기호를 클릭합니다(매개 변수 재정의 활성화
   1. 주소 필드를 클릭합니다.
   1. 다음 화면의 표현식 편집기에서 이메일 주소를 괄호 안에 넣고(*yourname@yourdomain*) 확인을 클릭합니다.
1. 여정을 테스트 모드로 전환합니다.
1. 다음 매개 변수로 이벤트를 트리거합니다.
   * 프로필 식별자를 다음으로 설정: 식별값: `a8f14eab3b483c2b96171b575ecd90b1`
   * 이벤트 유형: commerce.purchases
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 90845952-c2ea-4872-8466-5289183e4607
   * `SKU:` LLMH09
   * `City:`San Jose
   * `Postal Code:` 95119
   * `State`: CA
   * `Street:` 245 Park Avenue

사용자가 개인화된 구매 확인 이메일을 받게 됩니다.

* 제목란에는 테스트 프로필 이름인 &quot;Leora&quot;가 있어야 합니다.

* 이메일 본문은 다음과 같아야 합니다.

![이메일](/help/challenges/assets/c2-email.png)

>[!TAB 작업 확인]

**여정**

![여정](/help/challenges/assets/c2-journey.png)


**이메일**

**제목란:**

{{ profile.person.name.firstName }} 님, 구매해 주셔서 감사합니다!

**배송처 섹션:**

코드는 다음과 같아야 합니다.

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416*&#x200B;은 다른 번호입니다.

팁: 각 라인을 별도로 개인화합니다.

**주문 세부 사항 섹션:**

코드는 다음과 같아야 합니다.

Header:

```javascript
Order #: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**제품 목록:**

도우미 함수 &quot;each&quot;를 사용하여 제품 목록을 만듭니다. 테이블에 표시합니다. 코드는 다음과 같아야 합니다(`454181416` 대신 사용자의 이벤트 ID, `techmarketingdemos` 대신 사용자의 조직 등 사용자에게 해당하는 변수 표시).

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p></div></div></th></tr> {{/each}}
```

**주문 보기 버튼:**

`https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId={{context.journey.events.454181416.commerce.order.purchaseOrderNumber}}`

**가격 합계:**

합계:`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]