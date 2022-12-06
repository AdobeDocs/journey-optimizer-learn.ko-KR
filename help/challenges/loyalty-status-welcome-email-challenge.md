---
title: 충성도 상태 환영 이메일 만들기 - 문제
description: 여정 캔버스에서 여정을 작성하는 기본적인 방법을 이해합니다.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: e148101f8404c8e2019ee17823bcf1d7a9668bc5
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 4%

---

# 충성도 상태 환영 이메일 만들기 - 문제

![AJO 충성도 상태 환영 이메일 - 챌린지 배너](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 과제 | 충성도 상태 시작 이메일 만들기 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[세그먼트 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[세그먼트 자격 조건](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[HTML 콘텐츠 가져오기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html)</li></ul> |
| 다운로드할 자산 | [platinumStatusEmail.zip](/help/challenges/assets/email-assets/platinumStatusEmail.zip) |

## 더 스토리

Luma는 고객을 유치하고 유지하는 방법으로 충성도 프로그램을 제공합니다. 프로그램은 네 가지 다른 수준을 제공합니다. 청동, 은, 금, 백금. 각 충성도 계층은 반복 사업에 대한 보상으로 다양한 수준 또는 보상, 할인 및 기타 특별 혜택을 받습니다.

특별 백금 상태에 밑줄을 긋습니다. Luma는 플래티넘 계층에 도달하면 고객에게 환영 이메일을 보내려고 합니다.

## 과제

고객에게 백금 충성도 계층에 도달하면 환영 이메일을 자동으로 전송하는 여정을 설정하라는 메시지가 표시되었습니다.

>[!BEGINTABS]

>[!TAB 작업]

충성도 고객이 플래티넘 계층의 자격을 얻으면 축하 메시지를 받고 새로운 이점을 알려주어야 합니다. 크리에이티브 팀이 HTML 파일을 제공했습니다 **[Luma - 상태 업그레이드 - 시작 eMail](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** 이메일 본문으로 바꿉니다.

1. Journey Optimizer에서 `Luma – status upgrade`.
2. &#39;Luma - 새 상태 - 플래티넘&#39;이라는 여정을 만듭니다.
   1. 고객이 Platinum 충성도 계층의 자격을 얻으면 여정으로 이동합니다.
   2. 고객은 라는 이름의 이메일 메시지를 수신해야 합니다 `Luma – Platinum Status - Welcome`, 제목 줄 사용 `Welcome to Platinum Status, (recipient's first name)!` 창조 팀이 제공한 본체로
   3. HTML 파일을 업로드할 때 이메일이 &quot;백금&quot;이 아닌 &quot;다이아몬드&quot; 상태를 참조한다는 것을 알 수 있습니다. 크리에이티브 팀에 새 파일을 요청하지 않고 이메일 디자이너에서 이메일을 업데이트합니다.

>[팁!]
> Luma - Platinum Status - Welcome eMail이 트랜잭션인지 확인합니다.


>[!TAB 성공 기준]

여정 테스트:

1. 세그먼트 읽기 활동 에 네임스페이스가 **Luma CRM ID(lumaCrmId)**
2. 기본 이메일 매개 변수를 재정의하고 고유한 이메일 주소로 설정합니다

+++ 재정의 방법에 대한 자세한 내용을 보려면 여기를 클릭하십시오.
   * 눈 기호를 클릭하여 숨겨진 값을 표시합니다.
   * 전자 메일 매개 변수에서 T 기호를 클릭합니다(매개 변수 무시 활성화).

   ![전자 메일 매개 변수 무시](/help/challenges/assets/c3-override-email-paramters.jpg)

   * Address 필드를 클릭합니다.
   * 다음 화면에서는 이메일 주소를 괄호로 묶습니다. `"yourname@yourdomain"` 표현식 편집기에서 확인을 클릭합니다.
+++


3. 여정을 테스트 모드로 설정합니다
4. 이벤트 트리거
5. 프로필 식별자 필드에 Stanleigh Stoke용 다음 CRM ID를 추가합니다. `4f34057d9d9e792c28ba18ecae378e98`

개인화된 을 수신해야 합니다 *Luma - 플래티넘 상태 - 시작* 이메일.

>[!TAB 작업 확인]

여정 모습은 다음과 같습니다.

![platinum-status-upgrade-여정](/help/challenges/assets/journey-luma-status-upgrade.png)


다음은 이메일의 모습입니다.

![Luma - 상태 업그레이드 - 시작 eMail](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
