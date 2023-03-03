---
title: 여름 컬렉션 발표 만들기 - 과제
description: 새로운 Luma 여름 컬렉션을 홍보하기 위해 기존 고객 세그먼트에 여름 컬렉션 발표를 보냅니다.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 100%

---

# 여름 컬렉션 발표 만들기 - 과제

![AJO 여름 컬렉션 발표 배너](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| 과제 | 여름 컬렉션 발표 만들기 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[세그먼트 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ko)</li><li> [HTML 이메일 콘텐츠 가져오기 및 작성](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=ko)</li><li>[사용 사례 - 세그먼트 읽기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=ko)</li> |
| 다운로드할 자산 | [시즌 컬렉션 이메일 파일](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

{style=&quot;table-layout:auto&quot;}

## 스토리

가상의 스포츠 의류 회사인 Luma는 최신 의류 및 장비 컬렉션을 홍보하고 기존 고객에 대한 판매를 촉진하려고 합니다. Luma는 새로운 여름 컬렉션을 시작하며 특별히 다른 고객 세그먼트를 타겟팅하고 싶습니다.

## 과제

Luma 마케팅 팀이 Journey Optimizer에서 여름 컬렉션 마케팅 캠페인을 구현할 것을 요청합니다. 과제는 다음과 같습니다.

* 프로모션을 받을 프로필을 정의하는 세그먼트를 만듭니다.
* 여정 만들기.

### 1단계: 세그먼트 정의 - 활성 고객

>[!BEGINTABS]

>[!TAB 작업]

#### [!DNL Journey Optimizer]에서 세그먼트 만들기

* [!DNL Journey Optimizer]에서 *활성 고객*&#x200B;이라는 세그먼트 만들기
* 세그먼트는 활성 Luma 고객만 포함해야 합니다.
* 활성 고객은 Luma의 충성도 프로그램(브론즈, 실버, 골드 또는 플래티넘)에 티어가 있는 고객입니다.


>[!TAB 성공 기준]

세그먼트 빌더에서 자격 있는 프로필 수 추정치를 볼 수 있습니다. 교육용 샌드박스 데이터를 사용하여 작업하는 경우 1.29K 중 약 753개의 자격을 갖춘 프로필이 있습니다.

>[!NOTE]
>기존 프로필을 다시 채워야 하므로 기존 프로필에 대해 세그먼트 멤버십이 표시되는 데 최대 24시간이 걸릴 수 있습니다.

**자격을 갖춘 프로필이 세그먼트에 추가되었습니다.**

세그먼트 세부 사항 보기에 나열된 프로필 중 하나로 이동하여 세그먼트 자격에 추가된 프로필을 확인할 수 있습니다.

프로필 페이지에서 [!UICONTROL 속성] 탭을 사용하여 자격이 있는지 확인합니다. 티어는 실버, 골드, 플래티넘 또는 다이아몬드여야 합니다.

![프로필 속성](assets/C1-S1-profile-attributes.png)

또한 [!UICONTROL 세그먼트 멤버십] 탭에서 세그먼트가 나열되어 있는지 확인합니다.

![세그먼트 멤버십](assets/C1-S1-profile-segment-membership.png)

>[!TAB 작업 확인]

세그먼트 필드: **[!UICONTROL 속성]** > **[!UICONTROL XDM 개별 프로필]** > **[!UICONTROL 충성도]** > **[!UICONTROL 티어]**

세그먼트는 다음과 같아야 합니다.

![세그먼트 - 활성 고객](/help/challenges/assets/C1-S1.png)

코드는 다음과 같아야 합니다.

```javascript
stringCompare("equals", loyalty.tier, ["diamond", "gold", "platinum", "silver"], false)
```

>[!ENDTABS]


### 2단계: 여정 만들기 - 여름 컬렉션 발표

>[!BEGINTABS]

>[!TAB 작업]

#### 여름 컬렉션 발표 보내기

에이전시가 이메일 디자인이 포함된 4개의 HTML 파일을 제공했습니다.

* `SeasonalCollectionEmail.html`
* Luma 남성 컬렉션 이메일
* Luma 여성 컬렉션 이메일
* Luma - 20% 할인 컬렉션 이메일

1. [시즌 컬렉션 이메일 파일을 다운로드합니다](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

1. *Luma - 여름 컬렉션 발표*&#x200B;라는 여정 만들기는 다음 지침을 기반으로 합니다.

   1. 대상자의 10%를 컨트롤 그룹으로 유지하면서 *Luma - 새로운 여름 컬렉션 발표* 이메일을 *활성 고객* 세그먼트에 보냅니다.
      * 메시지 제목 *Luma - 여름 컬렉션 발표*
      * 제목란 *(수신인 이름) 님, 새로운 Luma 여름 컬렉션이 나왔습니다!*
      * 제공된 HTML 파일 `SeasonalCollectionEmail.html`을 이메일 본문에 사용합니다.
   1. 이틀 동안 기다렸다가 더 많은 타겟팅된 컨텐츠가 있는 후속 이메일 메시지를 보냅니다.
      * 남성 고객은 **Luma 남성 컬렉션** 이메일을 받습니다.
         * 메시지 제목: *Luma 남성 컬렉션*
         * 제목란: *(수신인 이름) 님, 새로운 남성용 운동복을 살펴보세요!*
         * 이메일 본문: `MensCollectionEmail.html` 이메일 본문에 사용됩니다.
      * 여성 고객은 **Luma 여성 컬렉션** 이메일을 받습니다.
         * 메시지 제목: *Luma 여성 컬렉션*
         * 제목란: *(수신인 이름) 님, Luma의 여성 컬렉션을 살펴보세요!*
         * 이메일 본문: `WomensCollectionEmail.html`
      * 다른 고객은 **Luma - 20% 할인 컬렉션** 이메일을 받습니다.
      * 메시지 제목: *Luma - 20% 할인 컬렉션*
      * 제목란: *(수신인 이름) 님, 20% 할인을 받으세요!*
      * 이메일 본문: `20OOffCollectionEmail.html`
   1. 상단의 타겟팅된 이메일을 보낸 후 이메일이 열릴 때까지 2일 기다립니다.
   1. 타겟팅된 이메일이 2일 이내에 열리지 않으면 최종 재타겟팅 시도로서 **Luma - 20 % 할인 컬렉션 이메일**&#x200B;을 보냅니다.


>[!TAB 성공 기준]

#### 이메일 미리 보기

**이메일 메시지 #1 - Luma - 여름 컬렉션 발표**

이메일 미리 보기:

1. 테스트 프로필 추가: Louise Petti:
   * ID 네임스페이스: *Luma CRM ID*
   * ID 값: *d1f132f9f9502bba047a6ec86c4b61f9*

결과:

* 제목란은 다음과 같아야 합니다. Louise 님, 새로운 Luma 컬렉션이 나왔습니다!
* 이메일 본문은 미리 보기와 일치해야 합니다. [새로운 시즌 컬렉션 발표](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)

**이메일 메시지 #2 - Luma 남성 컬렉션**

교정 보내기:

1. 테스트 프로필 추가: Stanleigh Stooke:
   * ID 네임스페이스: *Luma CRM ID*
   * ID 값: `4f34057d9d9e792c28ba18ecae378e98`
1. 테스트 프로필 Stanleigh Stooke를 선택합니다.
1. 교정을 보냅니다.

결과:\
이메일을 받습니다. 제목란은 다음과 같아야 합니다. *Stanleigh 님, 새로운 남성용 운동복을 살펴보세요!*&#x200B;그리고 이메일 본문은 미리 보기와 일치해야 합니다. [Luma 남성 컬렉션](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>교정을 받을 때까지 2분 정도 걸릴 수 있습니다.

**이메일 메시지 #3 - Luma 여성 컬렉션**

 *Louise Petti*&#x200B;의 테스트 프로필로 이메일 미리 보기.

* 제목란은 다음과 같아야 합니다. *Louise 님, Luma의 여성 콜렉션을 살펴보세요!*
* 이메일 본문은 미리 보기와 일치해야 합니다. [Luma 여성 컬렉션](/help/challenges/assets/email-assets/WomensCollectionEmail.html)

**이메일 메시지 #4 - Luma 20% 할인 컬렉션**

 *Louise Petti*&#x200B;의 테스트 프로필로 이메일 미리 보기.

*   제목란은 다음과 같아야 합니다. *Louise 님, 20% 할인을 받으세요!*
* 이메일 본문은 미리 보기와 일치해야 합니다. [Luma 20% 할인 컬렉션](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)

#### 여정 테스트

>[!IMPORTANT]
>
>여정을 테스트 모드로 설정하기 전에
>
>1. [!UICONTROL 세그먼트 활동 읽기]에 **Luma CRM ID(lumaCrmId)**&#x200B;로 설정된 네임스페이스가 있는지 확인합니다.
>1. 각각의 이메일에 대해 자신의 이메일 주소로 전송할 수 있도록 기본 이메일 매개 변수를 재정의합니다.
   >    * 눈 기호를 클릭하여 숨겨진 값을 표시합니다.
   >    * 이메일 매개 변수에서 T 기호를 클릭합니다(매개 변수 재정의 활성화).

      >
      >      ![이메일 매개 변수 재정의](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * [!UICONTROL 주소] 필드를 클릭합니다.
   >    * 다음 화면에서는 표현식 편집기에서 이메일 주소를 괄호 안에 넣고(`"yourname@yourdomain"`) 확인을 클릭합니다.

>


여정을 테스트하고 자신의 계정으로 이메일을 전송합니다.

1. 여정을 테스트 모드로 전환합니다.
1. **[!UICONTROL 한 번에 하나의 프로필]**&#x200B;을 선택합니다.
1. 대기 시간: 타이머를 120초로 설정합니다(필드에 입력).
1. 프로필 시작 트리거
1. 다음 *Luma CRM ID* 중 하나를 프로필 식별자로서 사용하여 각 분기를 테스트할 수 있습니다.
   * 여성: Leora Dietsche, ID 값:`a8f14eab3b483c2b96171b575ecd90b1`
   * 남성: Stanleigh Stooke, ID 값: `4f34057d9d9e792c28ba18ecae378e98`
   * 성별 미지정: Louise Petti, ID 값: `d1f132f9f9502bba047a6ec86c4b61f9`

1. 프로필 시작을 트리거하면 첫 번째 이메일을 받게 됩니다. 헤더는 사용자가 선택한 프로필에 따라 개인화되어야 합니다.
1. 여정은 각 분기로 계속 실행되어야 하며 사용자는 관련된 이메일을 받게 됩니다(예: *Jenna*&#x200B;를 선택한 경우, *Luma 여성 컬렉션* 이메일 수신).
1. 두 번째 이메일을 열면 여정이 종료됩니다.
1. 4단계를 반복할 수 있습니다. - 7. 3개 프로필 모두에 대해 분기가 올바르게 작동하는지 확인합니다.
1. 시간 초과를 테스트하려면 대기 시간을 30초로 설정하고 시작을 다시 트리거합니다.
1. 받은 이메일을 열지 말고(이메일을 미리 보지 마십시오(!)) 대기 시간이 지나도록 놔둡니다.

다음 이메일을 수신해야 합니다.

* Luma - 새로운 시즌 컬렉션 발표
* 사용한 테스트 프로필에 따라 다음 이메일 중 하나를 수신해야 합니다.
   * Leora: Luma 여성 컬렉션
   * Stanleigh: Luma 남성 컬렉션
   * Louise: Luma - 20% 할인 컬렉션
* 두 번째 이메일을 열지 않은 경우: Luma - 20% 할인 컬렉션

>[!TAB 작업 확인]

여정은 다음과 같아야 합니다.

![여정](/help/challenges/assets/c3-j1-journey.png)

**조건 - 컨트롤 그룹:**

![컨트롤 그룹](/help/challenges/assets/c3-j1-condition-control-group.png)

**조건 - 성별:**\

![조건 - 성별](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
