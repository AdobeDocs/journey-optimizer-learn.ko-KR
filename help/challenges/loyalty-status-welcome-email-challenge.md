---
title: 충성도 상태 환영 이메일 만들기 - 과제
description: 고객이 충성 티어에 도달하면 자동으로 환영 이메일을 보내는 여정을 작성합니다.
jira: KT-8109
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: ht
source-wordcount: '403'
ht-degree: 100%

---

# 충성도 상태 환영 이메일 만들기 - 과제

| 과제 | 충성도 상태 환영 이메일 만들기 |
|---|---|
| 페르소나 | 여정 관리자 |
| 필요한 기술 | <ul><li>[세그먼트 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ko)</li> <li>[세그먼트 선별](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journeys/use-case-read-segment-qualification.html?lang=ko)</li><li>[HTML 콘텐츠 가져오기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=ko)</li></ul> |
| 다운로드할 자산 | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style="table-layout:auto"}

## 스토리

Luma는 고객을 유치하고 유지하기 위한 방법으로 충성도 프로그램을 제공합니다. 이 프로그램에는 브론즈, 실버, 골드, 플래티넘의 4가지 티어가 있습니다. 각 충성도 티어는 지속적인 이용에 대한 보상으로 다양한 보상, 할인 및 기타 특별 혜택을 받습니다.

특별한 플래티넘 상태를 강조하기 위해 Luma는 플래티넘 티어에 도달한 고객에게 환영 이메일을 보내려고 합니다.

## 과제

고객이 플래티넘 충성도 티어에 도달하면 환영 이메일을 자동으로 전송하는 여정을 설정하라는 요청을 받았습니다.

>[!BEGINTABS]

>[!TAB 작업]

충성 고객이 플래티넘 티어가 되면 축하와 함께 새로운 혜택을 알려주는 이메일을 받아야 합니다. 크리에이티브 팀에서 이메일 본문이 있는 **[Luma - 상태 업그레이드 - 환영 이메일](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** HTML 파일을 제공했습니다.

1. Journey Optimizer에서 `Luma - platinum status`(이)라는 [!UICONTROL 세그먼트] 만들기

1. `Luma - New Status - platinum`(이)라는 여정을 만듭니다.

   1. 고객이 플래티넘 충성도 티어 자격을 갖추면 여정으로 이동합니다.

   1. 고객은 `Welcome to Platinum Status, {firstName}!`(이)라는 제목란과 크리에이티브 팀이 제공한 이메일 본문으로 구성된 `Luma - Platinum Status - Welcome`(이)라는 이메일 메시지를 수신해야 합니다. 이것은 [!UICONTROL 트랜잭션] 이메일입니다.

   1. HTML 파일을 업로드할 때 이메일이 “플래티넘”이 아닌 “다이아몬드” 상태를 참조한다는 것을 알 수 있습니다. 크리에이티브 팀에 새 파일을 요청할 필요 없이 [!UICONTROL 이메일 디자이너]에서 이메일을 업데이트합니다.

>[!TAB 성공 기준]

여정 테스트:

1. [!UICONTROL 세그먼트 활동 읽기]의 [!UICONTROL 네임스페이스]가 **[!DNL Luma CRM id(lumaCrmId)]**&#x200B;로 설정되어 있는지 확인합니다.

1. 기본 [!UICONTROL 이메일 매개 변수]를 재정의하여 자신의 이메일 주소로 설정합니다.
   * **[!UICONTROL 이메일 매개 변수]**&#x200B;에서 T 기호를 클릭합니다(매개 변수 재정의 활성화).

   * **[!UICONTROL 주소]** 필드를 클릭합니다.

   * 다음 화면에서는 표현식 편집기에서 이메일 주소를 괄호 안에 넣고(`"yourname@yourdomain"`) **[!UICONTROL 확인]**&#x200B;을 클릭합니다.

1. 여정을 테스트 모드로 설정합니다.

1. **[!UICONTROL 이벤트 트리거]**&#x200B;를 선택합니다.

1. **[!UICONTROL 프로필 식별자]** 필드에 다음과 같이 `Stanleigh Stooke`에 대한 `CRM ID`를 추가합니다. `4f34057d9d9e792c28ba18ecae378e98`

**결과:** 개인화된 *Luma - 플래티넘 상태 - 환영* 이메일을 수신해야 합니다.

이메일은 다음과 같아야 합니다.

![Luma - 상태 업그레이드 - 환영 이메일](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB 작업 확인]

성공 시 세그먼트의 모습:

![Luma - 플래티넘 상태 - 세그먼트](/help/challenges/assets/segment-luma-platinum-status.png)

여정은 다음과 같아야 합니다.

![플래티넘-상태-업그레이드-여정](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
