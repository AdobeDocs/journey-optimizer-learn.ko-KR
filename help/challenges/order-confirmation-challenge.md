---
title: 주문 확인 이메일 만들기
description: 트랜잭션 메시지를 만들고 개인화하는 방법에 대한 지식을 테스트합니다
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 4268144ade6588e48fc38cae7e542c227af96827
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 5%

---


# 주문 확인 이메일 만들기

![주문 확인](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| 과제 | 주문 확인 트랜잭션 이메일 만들기 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[메시지 편집기로 이메일 콘텐츠 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[개인화에 컨텍스트 기반 이벤트 정보 사용](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[개인화에 도우미 기능 사용](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| 다운로드할 자산 | [주문 확인 자산](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## 더 스토리

Luma는 온라인 스토어를 시작하고 고객이 주문을 하면 주문 확인 이메일을 제공하여 고객 경험을 향상하고자 합니다.



## 과제

Luma 고객이 온라인 주문을 완료하면 주문 확인 이메일을 보내는 여정을 만듭니다. 루마

>[!BEGINTABS]

>[!TAB 작업]

1. 라는 여정 만들기 `Luma - Order Confirmation`
2. 이벤트 사용: `LumaOnlinePurchase` 트리거로
3. 라는 주문 확인 이메일을 만듭니다. `Luma - Order Confirmation`:

* 카테고리 트랜잭션 - 트랜잭션 이메일 면을 선택해야 합니다.
* 제목란은 수신자의 이름으로 개인화되어야 하며 &quot;구매에 대한 감사&quot; 구문을 포함해야 합니다
* 를 사용하십시오 `Luma - Order summary` 템플릿 및 수정:

이메일은 다음과 같이 구조화해야 합니다.
<table>
<tr>
<td>
  <div>
     <strong> 헤더 섹션</strong>
      </div>
  </td>
  <td>
    <strong>Luma 로고</strong>
      <p>
     <li>luma_logo.png</li>
    <li>luma 웹 사이트에 대한 링크가 있어야 합니다. https://publish1034.adobedemo.com/content/luma/us/en.html</li>
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
    <em>안녕하세요. {first name}</em><p>
    <li>정렬: 왼쪽  </li>
   <li>텍스트 색상: rgb(69, 97, 162) #4461a2; 
   <li>글꼴 크기: 20px</li>
   <div>
    <p>
     <em>주문하셨습니다.
    <p>패키지가 전송되면 주문을 추적할 수 있도록 추적 번호가 포함된 이메일을 보냅니다.</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong> 납품처 섹션</strong>
      </div>
      <p><li>템플릿의 하드 코딩된 주소를 배송 주소로 바꿉니다 
      <li>주소 세부 사항은 이벤트(거리, 도시, 우편 번호, 주)의 컨텍스트 속성입니다
      <li>프로필의 이름과 성은
      <li> 할인, 합계, 도착 제거</p>
  </td>
  <td>
  <p> 납품처:</p>
      <em>이름 성<br>
     주소</em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>주문 세부 사항 섹션</strong>
      </div>
       <p><li>다음 항목 뒤에 이 섹션 추가 <b>납품처</b> 섹션 및 <b>주문 보기</b> 버튼을 클릭합니다.
      </p><br>
      <p><b>팁:</b>
      <li>상황에 맞는 이벤트 정보입니다.
      <li>[!UICONTROL helper 함수] 사용: [!UICONTROL 각]
      <li>코드 편집기 형식으로 전환하여 컨텍스트 데이터를 추가합니다.
      <li>DIV 태그를 사용하여 컨테이너에 정보를 넣습니다.
  </td>
  <td>
    <strong>Header</strong>
    <p>
    <em>순서: 'purchaseOrderNumber'</em>
    </p>
    <strong>순서가 지정된 제품 목록:
  </strong>
  <p>각 항목의 형식은 다음과 같이 지정해야 합니다.
   <img alt="주문" src="./assets/c2-order.png"> 
</p>
<strong>제품 이미지:</strong>
<li>클래스: 장바구니 항목 의자
<li>스타일: 테두리 상자: min-height:40px</li>
<li>위쪽 및 아래쪽 패딩:20px</li>
<li>padding-left:80px</li>
<li>테두리 반경:0px</li>
<li>을 컨테이너의 배경 이미지로 사용합니다</li>
<li>배경 위치: 0% 50%</li>
<li>배경 크기: 60px</li>
<li>background-repeat: 반복되지 않음</li>
<p>
<strong>가격:</strong>
<li>형식 = H5</li>
<li>style = box-sizing:border-box</li>
<li>margin-bottom:5px</li>
<li>margin-top:0px;</li>
<p>
<strong>이름 및 수량:</strong>
<li>class=text-small</li>
<li>style=box 크기 조정: 테두리 상자</li>
<li>padding-top: 5px</li>
<li>색상: rgb(101, 106, 119)</li>
<li>글꼴 크기:14px</li>
<p>
</td>
  </tr>
</table>


>[!TIP]
>
>여정 문제를 해결할 수 있도록 하기 위해 가장 좋은 방법은 시간 제한이나 오류가 발생할 경우 모든 메시지 작업에 대체 경로를 추가하는 것입니다.

>[!TAB 성공 기준]

테스트 모드에서 만든 여정을 트리거하고 직접 이메일을 전송합니다.

1. 눈 기호를 클릭하여 숨겨진 값을 표시합니다.
   1. 전자 메일 매개 변수에서 T 기호를 클릭합니다(매개 변수 무시 활성화).
      ![전자 메일 매개 변수 무시](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. Address 필드를 클릭합니다.
   3. 다음 화면에서는 이메일 주소를 괄호로 묶습니다. *yourname@yourdomain* 표현식 편집기에서 확인을 클릭합니다.
2. 여정을 테스트 모드로 전환합니다.
3. 다음 매개 변수로 이벤트를 트리거합니다.
   * 프로필 식별자를 다음으로 설정: ID 값:`a8f14eab3b483c2b96171b575ecd90b1`
   * 이벤트 유형: commerce.purchases
   * 이름: 스프라이트 요가 컴패니언 키트
   * 수량: 1
   * `Price Total:` 61
   * `Purchase Order Number:` 6253728
   * `SKU:` 24-WG080
   * `productImageURL:` <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>
   * `City:` San Jose
   * `Postal Code:` 95110
   * `State`: CA
   * `Street:` 345 공원가

지정된 제품과 함께 개인화된 구매 확인 이메일을 받게 됩니다.

* 제목 줄에는 테스트 프로필의 이름이 있어야 합니다. 레오라
* 주문 세부 사항 섹션은 테스트 중에 입력한 주문 세부 사항으로 채워야 합니다

>[!TAB 작업 확인]

**여정**

![여정](/help/challenges/assets/c2-journey.png)


**이메일**

**제목 줄:**

{{ profile.person.name.firstName }}감사합니다!

**납품처 섹션:**

다음은 코드가 있어야 하는 모습입니다.

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* 다른 번호가 될 것입니다.

팁: 개별 라인 개인화

**주문 세부 사항 섹션:**

![주문 세부 사항 섹션](/help/challenges/assets/c2-order-detail-section.png)

다음은 코드가 있어야 하는 모습입니다.

Header:

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**제품 목록:**

도우미 함수 &quot;each&quot;를 사용하여 제품 목록을 만듭니다. 표에 표시합니다. 다음은 코드가 있어야 하는 모습입니다.

```javascript
<div class="text-container" contenteditable="true">
  <p><span class="acr-expression-field" contenteditable="false">{{#each context.journey.events.454181416.productListItems as |product|}}
    </span></p>
  <div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
    <h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</h5>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</div>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div>
  </div>
  <div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
  {{/each}}<p></p>
  <p></p>
</div>
```

**가격 합계:**

합계:`${{context.journey.events.1627840522.commerce.order.priceTotal}}`

**고객 정보 섹션**

![고객 주소](assets/c2-customer-information.png)

개인화는 다음과 같습니다.

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

>[!ENDTABS]