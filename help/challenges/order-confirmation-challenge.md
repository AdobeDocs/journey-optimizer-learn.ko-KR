---
title: 주문 확인 이메일 만들기
description: 트랜잭션 메시지를 만들고 개인화하는 방법에 대한 지식을 테스트합니다.
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 02625ddf2348f2754c821c8e49a1e70154fd6e63
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 50%

---


# 주문 확인 이메일 만들기

![주문 확인](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 과제 | 주문 확인 트랜잭션 이메일 만들기 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[메시지 편집기로 이메일 콘텐츠 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/create-content-with-the-email-designer.html?lang=en)</li> <li>[개인화에 컨텍스트 기반 이벤트 정보 사용](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=ko)</li><li>[개인화에 도우미 기능 사용](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=ko)</li></ul> |
| 다운로드할 자산 | [주문 확인 자산](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## 스토리

Luma는 온라인 스토어를 시작하고 고객이 주문을 하면 주문 확인 이메일을 제공하여 고객 경험을 향상하고자 합니다.



## 과제

Luma 고객이 온라인 주문을 완료하면 주문 확인 이메일을 보내는 여정을 만듭니다.

>[!BEGINTABS]

>[!TAB 작업]

1. `Luma - Order Confirmation`(이)라는 여정 만들기
2. 이벤트 사용: `LumaOnlinePurchase`
3. 만들기 **트랜잭션**  이메일 호출 `Luma - Order Confirmation`

* &quot;구매해주셔서 감사합니다, `FirstName`&quot;
* `Luma - Order summary` 템플릿을 사용하고 수정하십시오.
   * 제거 `You may also like` 섹션
   * 이메일 하단에 가입 해지 링크를 추가합니다

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
    <li>luma 웹 사이트에 연결해야 합니다. https://luma.enablementadobe.com/content/luma/us/en.html</li>
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
    <em>안녕하세요. {firstName}</em><p>
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
      <li>템플릿의 하드 코딩된 주소를 <b>배송 주소</b>
      <li>주소 세부 사항은 이벤트(1, city, 우편 번호, 주)의 컨텍스트 속성입니다
      <li> 제거 <i>할인, 합계, 도착</i></p>
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
       <p><li>아래에 이 섹션을 추가합니다. <b>납품처</b> 섹션을 참조하십시오.
      </p><br>
      <p><b>팁:</b>
      <li>구조 구성 요소 사용 <b>1:2열 왼쪽</b> 이 섹션
      <li>컨텍스트 기반 이벤트 정보입니다.
      <li>[!UICONTROL helper function] 사용: [!UICONTROL Each]
      <li>코드 편집기 형식으로 전환하여 컨텍스트 데이터를 추가합니다.
  </td>
  <td>
    <strong>Header</strong>
    <p>
  순서: <em>{purchaseOrderNumber}</em>
    </p>
    <strong>주문 제품 목록:
  </strong>
  <p>각 제품을 이미지, 가격 및 이름으로 순서대로 나열합니다.
  <p>각 항목의 레이아웃은 다음과 같습니다.
   <img alt="주문" src="./assets/c2-order.png"> 
<p><b>장바구니에 링크 추가</b>
<p>URL의 주문 ID를 구매 발주 번호로 바꿉니다.
   <i>https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId=90845952-c2ea-4872-8466-5289183e4607</i>
</td>
  </tr>
</table>


>[!TIP]
>
>여정 문제를 해결할 수 있도록 하기 위해, 시간 초과 또는 오류가 있는 경우 모든 메시지 작업에 대체 경로를 추가하는 것이 좋습니다.

>[!TAB 성공 기준]

테스트 모드에서 만든 여정을 트리거하고 직접 이메일을 전송합니다.

1. 테스트 모드로 전환하기 전에 전자 메일 매개 변수를 무시하여 테스트 전자 메일을 전자 메일 주소로 보냅니다.
   1. 전자 메일 세부 사항 보기를 엽니다.
   2. 전자 메일 매개 변수 섹션에서 T 기호를 클릭합니다(매개 변수 무시 활성화)
   3. 주소 필드를 클릭합니다.
   4. 다음 화면에서는 이메일 주소를 괄호로 묶습니다. *&quot;yourname@yourdomain&quot;* 표현식 편집기에서 확인을 클릭합니다.
2. 여정을 테스트 모드로 전환합니다.
3. 다음 매개 변수로 이벤트를 트리거합니다.
   * 프로필 식별자를 다음으로 설정: 식별값: `a8f14eab3b483c2b96171b575ecd90b1`
   * 이벤트 유형: commerce.purchases
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 90845952-c2ea-4872-8466-5289183e4607
   * `SKU:` LLMH09
   * `City:`San Jose
   * `Postal Code:` 95119
   * `State`: CA
   * `Street:` 245 파크 애비뉴

개인화된 구매 확인 이메일을 받게 됩니다.

* 제목란에는 테스트 프로필 이름인 &quot;Leora&quot;가 있어야 합니다.

* 이메일 본문은 다음과 같습니다.

![이메일](/help/challenges/assets/c2-email.png)

>[!TAB 작업 확인]

**여정**

![여정](/help/challenges/assets/c2-journey.png)


**이메일**

**제목란:**

구매해주셔서 감사합니다 {{ profile.person.name.firstName }}!

**배송처 섹션:**

코드는 다음과 같아야 합니다.

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* 는 다른 번호입니다.

팁: 각 라인을 별도로 개인화합니다.

**주문 세부 사항 섹션:**

코드는 다음과 같아야 합니다.

Header:

```javascript
Order #: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**제품 목록:**

도우미 함수 &quot;each&quot;를 사용하여 제품 목록을 만듭니다. 테이블에 표시합니다. 이렇게 하면 코드가 다음과 같이 표시됩니다(예: 이벤트 ID 사용). 대신 `454181416` 및 사용자 조직 ID가 아닌 `techmarketingdemos` ):

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p></div></div></th></tr> {{/each}}
```

**주문 보기 단추:**

`https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId={{context.journey.events.454181416.commerce.order.purchaseOrderNumber}}`

**가격 합계:**

합계:`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]