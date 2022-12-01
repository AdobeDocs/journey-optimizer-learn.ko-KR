---
title: 제품 보충 챌린지
description: 세그먼트 만들기에 대해 학습한 내용을 적용하고 기술을 테스트합니다.
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 0e83d8fbad6bd87ed25980251970898cb5b94bc0
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 2%

---

# 제품 보충 챌린지

| 과제 | 제품 보충 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[세그먼트 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=en)</li><li> [HTML 이메일 콘텐츠 가져오기 및 작성](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=en)</li><li>[사용 사례 - 세그먼트 읽기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| 다운로드할 자산 | [계절별 컬렉션 전자 메일 파일](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## 그 이야기

Luma 웹 사이트를 탐색할 때 고객은 관심 있는 제품을 희망 목록에 추가할 수 있습니다. Luma가 타겟팅된 마케팅 메시지와 제품에 대한 정보를 고객에게 보낼 수 있도록 합니다.

## 과제

Luma는 이 항목이 다시 재고가 있을 때 이전에 재고 부족 상태였던 희망 목록에 항목이 있는 고객에게 알리는 Journey Optimizer의 여정을 구현하도록 요청합니다.

## 세그먼트 정의 - 재고 부족 Wishlist 항목

제품이 다시 시작될 때 관심이 있는 잠재 고객을 타겟팅하려면 고객으로 구성된 세그먼트를 만드십시오

* 원하는 목록에 하나 이상의 항목을 추가한 사용자(이벤트 유형 사용: [!UICONTROL 격자에 대한 상거래 저장])
* 어느 쪽이었습니까 **재고 부족** 최근 3개월(재고 수량 = 0 사용)
* 그리고 그 후 그 품목을 구매하지 않았습니다.

이 세그먼트 이름을 다음과 같이 지정합니다. *사용자 이름 - 재고 부족-Wishlist*

+++**작업 확인**

세그먼트는 다음과 같이 표시되어야 합니다.

![세그먼트 - 재고 부족 Wishlist 항목](/help/challenges/assets/C1-S2.png)

지난 3개월 동안 재고가 없는 항목을 원하는 목록에 추가한 고객:

* 이벤트: 래터용으로 저장
   * 최소 1개 포함
   * 재고 수량이 0인 경우

이후에 항목을 구매하지 않았습니다.

* SKU가 **나중에 사용하기 위해 저장 이벤트**.

>[!TIP]
> * Save for Later의 SKU를 *변수 찾아보기* 섹션
> * 나중에 사용할 수 있도록 저장 아래의 SKU를 이벤트 필드에 놓을 때 비교 옵션을 사용합니다


세그먼트 편집 화면의 이벤트 아래에서 오른쪽 아래 모서리에 있는 코드를 확인합니다. 코드는 다음과 같습니다.

코드:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

+++

### 이메일 생성 - Luma-Product 보충

품목이 재고로 돌아왔다는 것을 고객에게 알리고 쇼핑 시작 호출을 통해 재고 부족 항목을 추가한 고객에게 알립니다.

### 여정 만들기 - 제품 잠금 알림

이전에 재고 부족 항목이 다시 재고가 있는 경우, 품목이 다시 재고가 있기 때문에 쇼핑 시작 호출로 재고 부족 항목을 추가한 고객에게 알립니다.

1. &quot;your name_Luma - Product Stock&quot;이라는 여정을 만듭니다.
1. 제품이 다시 재고가 있을 경우 여정을 트리거해야 합니다
1. 보내기 *Luma-제품 보충* 전자 메일 보낸 사람
1. 이 항목이 재고가 없는 동안 해당 항목에 추가된 사용자

>[!TIP]
>
> 기존 비즈니스 이벤트를 사용합니다. 잠금 SKU가 래터용 (임의) 이벤트 유형 저장에 포함되어 있는지 확인하는 조건을 추가해야 합니다.

+++**성공 기준**

여정 테스트:

1. 세그먼트 자격 이벤트에 Namespace = Email이 있는지 확인합니다.
1. 기본 이메일 매개 변수를 무시하고 고유한 이메일 주소로 설정합니다(지침은 이메일 #1 참조).
1. 여정을 테스트 모드로 설정합니다
1. 이벤트 트리거 - 다음 데이터를 입력합니다.

   * 설명: 화려한 기계와 값비싼 멤버십은 잊으세요 - 하모니 루플렉스 강도 밴드 키트는 놀라운 운동을 위해 필요한 모든 것입니다. 이 키트는 강화 및 토닝 연습의 범위에 필요한 모든 것을 가지고 있다.
   * 이름: 조화 루마플렉스 강도 밴드 키트
   * 가격: 22
   * 제품 ID: 24UG03
   * 제품 이미지 URL: https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24UG03
   * 스톡 이벤트 유형: 재채기
   * 프로필 식별자: Jenna_Palmer9530@emailsim.io

Luma 이메일 제품 보충&quot; 이메일을 제품 세부 사항과 Jana의 개인화와 함께 받아야 합니다.

+++

+++**작업 확인**

여정 모습은 다음과 같습니다.

![제품 보충 여정](/help/challenges/assets/c3-j3-journey.png)

조건: 위시리스트

![조건 - wishlist](/help/challenges/assets/c3-j3-condition.png)

조건 코드:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```

+++
