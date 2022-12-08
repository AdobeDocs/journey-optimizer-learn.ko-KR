---
title: 여름 컬렉션 발표 만들기 - 과제
description: 새로운 Luma Summer Collection을 홍보하기 위해 기존 고객의 세그먼트에 Summer Collection 알림을 보냅니다.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: cfd438e198fdf62859569eed0c6ac22087ddbc75
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 2%

---

# 여름 컬렉션 발표 만들기 - 과제

![AJO 여름 컬렉션 공지 배너](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| 과제 | 여름 컬렉션 발표 만들기 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[세그먼트 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [HTML 이메일 콘텐츠 가져오기 및 작성](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[사용 사례 - 세그먼트 읽기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| 다운로드할 자산 | [계절별 컬렉션 전자 메일 파일](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## 그 이야기

가상 운동복 회사인 루마는 최신 의류와 기어 컬렉션을 홍보하고 기존 고객을 위한 판매를 유도하고 있습니다. Luma는 새로운 Summer Collection을 시작하고 있으며 서로 다른 고객 세그먼트를 특별히 타겟팅하고 싶습니다.

## 고객의 과제

Luma 마케팅 팀은 Journey Optimizer에서 여름 컬렉션 마케팅 캠페인을 구현하도록 요청합니다. 고객의 과제는 다음과 같습니다.

* 프로모션을 받을 프로필을 정의하는 세그먼트를 만듭니다.
* 여정 만들기.

### 1단계: 세그먼트 정의 - 활성 고객

>[!BEGINTABS]

>[!TAB 작업]

#### 에서 세그먼트 만들기 [!DNL Journey Optimizer]

* 에서 세그먼트 만들기 [!DNL Journey Optimizer] called *활성 고객*.
* 세그먼트는 활성 Luma 고객만 포함해야 합니다.
* 활성 고객은 Luma의 충성도 프로그램(청동, 은, 금 또는 백금)에 계층이 있는 고객으로 정의됩니다.


>[!TAB 성공 기준]

세그먼트 빌더에서 예상 자격 있는 프로필 수를 볼 수 있습니다. 교육 샌드박스 데이터를 사용하여 작업하는 경우 1.29K에서 약 753개의 인증된 프로필이 있습니다.

>[!NOTE]
>기존 프로필을 다시 채워야 하므로 기존 프로필에 대해 세그먼트 멤버십이 표시되는 데 최대 24시간이 걸릴 수 있습니다.

**자격 있는 프로필이 세그먼트에 추가되었습니다.**

세그먼트의 세부 사항 보기에 나열된 프로필 중 하나로 이동하여 세그먼트 자격에 추가된 프로필을 확인할 수 있습니다.

프로필 페이지에서 [!UICONTROL 속성] 탭을 사용하여 자격이 있는지 확인합니다. 계층은 은, 금, 백금 또는 다이아몬드여야 합니다.

![프로필 속성](assets/C1-S1-profile-attributes.png)

또한 [!UICONTROL 세그먼트 멤버십] 탭: 세그먼트가 나열되어야 합니다.

![세그먼트 멤버십](assets/C1-S1-profile-segment-membership.png)

>[!TAB 작업 확인]

세그먼트 필드: [!UICONTROL 속성] > [!UICONTROL XDM 개별 프로필] > [!UICONTROL 충성도] > [!UICONTROL 계층]

세그먼트는 다음과 같이 표시되어야 합니다.

![세그먼트 - 활성 고객](/help/challenges/assets/C1-S1.png)

코드는 다음과 같습니다.

```javascript
stringCompare("equals", loyalty.tier, ["diamond", "gold", "platinum", "silver"], false)
```

>[!ENDTABS]


### 2단계: 여정 만들기 - 여름 컬렉션 발표

>[!BEGINTABS]

>[!TAB 작업]

#### 여름 컬렉션 알림 보내기

한 에이전시가 전자 메일 디자인이 포함된 4개의 HTML 파일을 제공했습니다.

* `SeasonalCollectionEmail.html`
* Luma Men&#39;s Collection 이메일
* Luma Women&#39;s Collection 이메일
* Luma - 컬렉션 이메일 20% 할인

1. [계절별 컬렉션 이메일 파일을 다운로드합니다](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

2. 라는 여정 만들기 *Luma - 여름 컬렉션 발표* 다음 지침을 기반으로 합니다.

   1. 보내기 *Luma - 새로운 여름 컬렉션 발표* 전자 메일 *활성 고객* 세그먼트, 대상자의 10%를 컨트롤 그룹으로 보유
      * 메시지 제목 *Luma - 여름 컬렉션 발표*
      * 제목 줄 *(수신자의 이름), 새로운 Luma 여름 컬렉션이 여기에 있습니다.*
      * 제공된 HTML 파일 사용 `SeasonalCollectionEmail.html` 이메일 본문에 사용됩니다.
   2. 이틀 동안 기다렸다가 더 많은 타깃팅된 컨텐츠가 있는 후속 이메일 메시지를 보냅니다.
      * 남성 고객은 **Luma Men&#39;s Collection** 이메일.
         * 메시지 제목: *Luma Men&#39;s Collection*
         * 제목 줄: *(수신자의 이름), 남성용 새로운 운동 장비를 살펴보십시오!*
         * 이메일 본문: `MensCollectionEmail.html` 이메일 본문에 사용됩니다.
      * 여성 고객은 **루마 여자 컬렉션** 이메일.
         * 메시지 제목: *루마 여자 컬렉션*
         * 제목 줄: *(수신자 이름), Luma&#39;s Women Collection을 살펴보십시오!*
         * 이메일 본문: `WomensCollectionEmail.html`
      * 다른 고객은 **Luma - 컬렉션 20% 해제** 이메일.
         * 메시지 제목: *Luma - 컬렉션 20% 해제*
         * 제목 줄: *(수신자 이름) 20% 할인 판매*
         * 이메일 본문: `20OOffCollectionEmail.html`
   3. 위에 타겟팅된 이메일을 보낸 후 이메일이 열릴 때까지 2일 기다립니다
   4. 타겟팅된 이메일이 2일 이내에 열리지 않으면 다음 주소로 **Luma - 20 %off 컬렉션 이메일** 최종 재타겟팅 시도로서


>[!TAB 성공 기준]

#### 이메일 미리 보기

**이메일 메시지 #1 - Luma - 여름 컬렉션 발표**

전자 메일 미리 보기:

1. 테스트 프로필 추가: 루이스 페티:
   1. ID 네임스페이스: *Luma CRM ID*
   2. ID 값: *d1f132f9f9502bba047a6ec86c4b61f9*

결과:
* 제목 줄에는 다음 내용이 포함되어야 합니다. 루이즈, 새로운 루마 컬렉션이 여기 있어!
* 이메일 본문은 미리 보기에서 본 이메일과 일치해야 합니다. [새로운 시즌 컬렉션 발표](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**이메일 메시지 #2 - Luma Men&#39;s Collection**

자신에게 증명 보내기:

1. 테스트 프로필 추가: 스탠레이 스토케:
   1. ID 네임스페이스: *Luma CRM ID*
   1. ID 값: `4f34057d9d9e792c28ba18ecae378e98`
1. 테스트 프로필을 선택합니다. 스탠리 스토커
1. 자신에게 증거를 보내라.

결과:\
이메일을 받아야 합니다. 제목란 *스탠리, 남성용 신운동복 살펴봐!* 및 이메일 본문은 미리 보기에서 본 내용과 일치해야 합니다. [Luma Men&#39;s Collection](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>증명을 받으려면 2분 정도 걸릴 수 있습니다.

**이메일 메시지 #3 - Luma Women&#39;s Collection**

테스트 프로필을 사용하여 이메일 미리 보기 *루이스 페티*

* 제목 줄에는 다음 내용이 포함되어야 합니다. *루이즈, 루마의 여성 콜렉션을 살펴보세요!*
* 이메일 본문은 미리 보기에서 본 이메일과 일치해야 합니다. [루마 여자 컬렉션](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**이메일 메시지 #4 - Luma 20% 오프 컬렉션**

테스트 프로필을 사용하여 이메일 미리 보기 *루이스 페티*

* 제목 줄에는 다음 내용이 포함되어야 합니다. *루이즈, 20%의 판매량을 즐기세요!*
* 이메일 본문은 미리 보기에서 본 이메일과 일치해야 합니다. [Luma 20% 오프 컬렉션](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)


#### 여정 테스트

>[!IMPORTANT]
>
>여정을 테스트 모드로 설정하기 전에:
>
>1. 다음을 확인합니다. [!UICONTROL 세그먼트 활동 읽기] 에는 네임스페이스가 **Luma CRM ID(lumaCrmId)**
>1. 각 이메일에 대해 이메일 주소로 전송하도록 이메일의 기본 이메일 매개 변수를 무시합니다.
   >    * 눈 기호를 클릭하여 숨겨진 값을 표시합니다.
   >    * 전자 메일 매개 변수에서 T 기호를 클릭합니다(매개 변수 무시 활성화).

      >
      >      ![전자 메일 매개 변수 무시](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * 을(를) 클릭하여 [!UICONTROL 주소] 필드
   >    * 다음 화면에서 이메일 주소를 괄호로 묶습니다. `"yourname@yourdomain"` 표현식 편집기에서 확인을 클릭합니다.

>


여정을 테스트하고 전자 메일을 자신의 계정에 전송하도록 합니다.

1. 여정을 테스트 모드로 전환합니다.
1. 한 번에 하나의 프로필을 선택합니다.
1. 대기 시간: 타이머를 120초로 설정합니다(필드에 입력).
1. 프로필 시작 트리거
1. 다음 중 하나를 사용하여 각 분기를 테스트할 수 있습니다 *Luma CRM Id* 프로필 식별자로서:
   * 여성: Leora Diitsche, ID 값:`a8f14eab3b483c2b96171b575ecd90b1`
   * 남성: Stanleigh Stooke, ID 값: `4f34057d9d9e792c28ba18ecae378e98`
   * 성별을 지정하지 않았습니다. Louise Petti, ID 값: `d1f132f9f9502bba047a6ec86c4b61f9`

1. 프로필 입력을 트리거하면 첫 번째 이메일을 받게 됩니다. 헤더는 사용자가 선택한 프로필에 따라 개인화되어야 합니다.
1. 여정은 각 분기로 계속 진행되어야 하며 관련 이메일을 받게 됩니다(예를 들어 를 선택한 경우) *제나*, 을 수신해야 합니다. *루마 여자 컬렉션* 이메일).
1. 두 번째 이메일을 엽니다. 그러면 여정이 종료됩니다.
1. 4단계를 반복할 수 있습니다. - 7. 3개 프로필 모두에 대해 분기가 올바르게 작동하는지 확인합니다.
1. 시간 초과를 테스트하려면 대기 시간을 30초로 설정하고 항목을 다시 트리거합니다.
1. 받은 전자 메일을 열지 않습니다(전자 메일(!)는 미리 보지 마십시오. 대기시간을 줄이게

다음 이메일을 수신해야 합니다.

* Luma - 새로운 시즌 컬렉션 발표
* 사용한 테스트 프로필에 따라 다음 이메일 중 하나를 수신해야 합니다.
   * 레오라: 루마 여자 컬렉션
   * 스탠리: Luma Men&#39;s Collection
   * 루이스: Luma - 20% 해제 컬렉션
* 두 번째 이메일을 열지 않은 경우: Luma - 20% 해제 컬렉션

>[!TAB 작업 확인]

여정 모습은 다음과 같습니다.

![여정](/help/challenges/assets/c3-j1-journey.png)

**조건 - 컨트롤 그룹:**

![컨트롤 그룹](/help/challenges/assets/c3-j1-condition-control-group.png)

**조건 - 성별:**\

![조건 - 성별](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
