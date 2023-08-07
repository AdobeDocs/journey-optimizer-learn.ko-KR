---
title: 제품 보충 과제
description: 세그먼트 만들기에 대해 학습한 내용을 적용하고 기술을 테스트합니다.
jira: KT-8417
feature: Segments
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 5c763ec877c75c07132f4cc714d63695e12638dc
workflow-type: ht
source-wordcount: '580'
ht-degree: 100%

---

# 제품 보충 과제

| 과제 | 제품 보충 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[세그먼트 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ko)</li><li> [HTML 이메일 콘텐츠 가져오기 및 작성](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=ko)</li><li>[사용 사례 - 세그먼트 읽기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=ko)</li> |
| 다운로드할 자산 | [제품 재입고 이메일 파일](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip) |

## 스토리

고객이 Luma 웹 사이트를 찾아볼 때 관심 있는 제품을 위시리스트에 추가하여 Luma가 타겟팅 마케팅 메시지 및 제품 정보를 고객에게 보내도록 허용할 수 있습니다.

## 과제

Luma는 Journey Optimizer에서 품절 상태였던 위시리스트 항목이 재입고되었을 때 고객에게 알리는 여정을 구현하도록 요청합니다. 크리에이티브 팀에서는 [제품 재입고 이메일 파일](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip)을 제공합니다.

>[!BEGINTABS]

>[!TAB 작업]

## 1. 세그먼트 정의 - 품절된 위시리스트 품목

제품이 재입고되면 관심을 가질 만한 잠재 고객을 타겟팅하기 위해 다음과 같은 고객으로 구성된 대상자를 만듭니다.

* 위시리스트에 하나 이상의 품목을 추가한 사람([!UICONTROL Commerce 나중을 위해 저장] 이벤트 유형 사용)
* 지난 3개월 동안 품절 상태(재고 수량 = 0 사용)
* 이후 해당 품목을 구매하지 않음.

>[!TIP]
>*나중을 위해 저장 이벤트*&#x200B;의 SKU와 SKU가 일치하는 모든 구매 이벤트 유형을 제외합니다. *변수 찾아보기* 섹션에서 필드를 찾을 수 있습니다.

세그먼트 이름 지정: `Out-of-stock-Wishlist`


### 2. 여정 만들기 - 제품 재입고 알림

이전에 품절된 항목이 재입고되는 경우, 품절 항목을 추가한 고객에게 쇼핑을 시작하라는 호출을 보내 해당 항목이 재입고된 것을 알려줍니다.

1. 여정 호출: `Product Restock`
2. 제품이 재입고되는 경우 여정을 트리거해야 합니다.
3. 다음 대상에게 *제품 재입고 이메일* 보내기:
4. 이 항목이 품절일 때 위시리스트에 추가한 사용자

>[!TAB 성공 기준]

여정 테스트:

1. 읽기 세그먼트 이벤트에 Namespace = `Luma CRM ID`이(가) 있는지 확인
1. 기본 이메일 매개 변수를 재정의하고 자신의 이메일 주소로 설정합니다(지침은 이메일 #1 참조).
1. 여정을 테스트 모드로 설정합니다
1. 이벤트 트리거 - 다음 데이터를 입력합니다.

   * 설명: 화려한 머신과 값비싼 멤버십은 잊으세요. Harmony Lumaflex 스트렝스 밴드 키트 하나만 있으면 효과적인 운동을 하실 수 있습니다. 이 키트는 근력 강화부터 토닝 운동에 필요한 모든 것이 있습니다.
   * 이름: Harmony Lumaflex 스트렝스 밴드 키트
   * 가격: 22
   * 제품 ID: 24-UG03
   * 제품 이미지 URL: https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24-UG03
   * 재고 이벤트 유형: 재입고
   * 프로필 식별자: Jenna_Palmer9530@emailsim.io

제품 세부 사항과 Jenna를 위한 맞춤형 &quot;Luma Email 제품 보충&quot; 이메일을 받게 됩니다.

>[!TAB 작업 확인]

세그먼트는 다음과 같아야 합니다.

![세그먼트 - 품절 위시리스트 항목](/help/challenges/assets/C1-S2.png)


여정은 다음과 같아야 합니다.

![제품 보충 여정](/help/challenges/assets/c3-j3-journey.png)

조건: 위시리스트 항목

![조건 - 위시리스트 항목](/help/challenges/assets/c3-j3-condition.png)

조건 코드:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```


>[!TIP]
> * *변수 찾아보기* 섹션의 [나중을 위해 저장]에서 SKU를 선택합니다.
> * [나중을 위해 저장] 아래 SKU를 이벤트 필드에 놓을 때 비교 옵션을 사용합니다.

[이벤트] 아래의 [세그먼트 편집] 화면에서 오른쪽 아래 모서리에 있는 코드를 확인합니다. 코드는 다음과 같아야 합니다.

코드:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

>[!ENDTABS]

### 이메일 생성 - Luma-제품 보충

품절 항목을 추가한 고객에게 쇼핑을 시작하라는 호출을 보내 해당 항목이 재입고된 것을 알립니다.



>[!TIP]
>
> 기존 비즈니스 이벤트를 사용합니다. 나중을 위해 저장 이벤트 유형에 재입고 SKU가 포함되어 있는지 확인하는 조건문을 추가합니다.
>




