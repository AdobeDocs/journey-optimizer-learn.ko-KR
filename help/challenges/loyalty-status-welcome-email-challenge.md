---
title: 충성도 상태 환영 이메일 만들기 - 과제
description: 여정 캔버스에서 여정을 작성하는 기본적인 방법을 이해합니다.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 2bddc86066f265cda1d2063db8eb37c9f211eb76
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 86%

---

# 충성도 상태 환영 이메일 만들기 - 과제

![충성도 상태 환영 이메일 - 과제 배너](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| 과제 | 충성도 상태 환영 이메일 만들기 |
|---|---|
| 담당자 | 여정 관리자 |
| 필요한 기술 | <ul><li>[세그먼트 만들기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=ko)</li> <li>[세그먼트 자격 조건](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=ko)</li><li>[HTML 콘텐츠 가져오기](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=ko)</li></ul> |
| 다운로드할 자산 | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

## 스토리

Luma는 고객을 유치하고 유지하기 위한 방법으로 충성도 프로그램을 제공합니다. 이 프로그램에는 브론즈, 실버, 골드, 플래티넘의 4가지 티어가 있습니다. 각 충성도 티어는 지속적인 이용에 대한 보상으로 다양한 보상, 할인 및 기타 특별 혜택을 받습니다.

특별 플래티넘 상태에 밑줄을 긋습니다. Luma는 플래티넘 티어에 도달한 고객에게 환영 이메일을 보내려고 합니다.

## 과제

고객이 플래티넘 충성도 티어에 도달하면 환영 이메일을 자동으로 전송하는 여정을 설정하라는 요청을 받았습니다.

>[!BEGINTABS]

>[!TAB 작업]

충성도 고객이 플래티넘 계층의 자격을 얻으면 축하 이메일을 받고 새로운 이점을 알려주어야 합니다. 크리에이티브 팀이 **[Luma - 상태 업그레이드 - 환영 이메일](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** HTML 파일과 이메일 본문을 제공했습니다.

1. Journey Optimizer에서 `Luma – platinum status`(이)라는 [!UICONTROL 세그먼트] 만들기
2. `Luma – New Status – platinum`(이)라는 여정을 만듭니다.
   1. 고객이 플래티넘 충성도 티어가 됐을 때 여정으로 이동합니다.
   2. 고객은 `Welcome to Platinum Status, {firstName}!`(이)라는 제목란과 크리에이티브 팀이 제공한 이메일 본문으로 구성된 `Luma – Platinum Status - Welcome`(이)라는 이메일 메시지를 수신해야 합니다. 이것은 [!UICONTROL 트랜잭션] 이메일입니다.
   3. HTML 파일을 업로드할 때 이메일이 “플래티넘”이 아닌 “다이아몬드” 상태를 참조한다는 것을 알 수 있습니다. 크리에이티브 팀에 새 파일을 요청하지 않고 [!UICONTROL 이메일 디자이너].

>[!TAB 성공 기준]

여정 테스트:

1. [!UICONTROL 세그먼트 활동 읽기]에 **[!DNL Luma CRM id(lumaCrmId)]**(으)로 설정된 [!UICONTROL 네임스페이스]가 있는지 확인합니다.
2. [!UICONTROL 이메일 매개 변수] 기본값을 재정의하고 자신의 이메일 주소로 설정하십시오.
   * [!UICONTROL 이메일 매개 변수]에서 T 기호를 클릭합니다(매개 변수 재정의 활성화).
   *  [!UICONTROL 주소 필드]를 클릭합니다.
   * 다음 화면에서는 표현식 편집기에서 이메일 주소를 괄호 안에 넣고(`"yourname@yourdomain"`) 확인을 클릭합니다.
3. 여정을 테스트 모드로 설정합니다
4. 선택 **이벤트 트리거**
5. [!UICONTROL 프로필 식별자] 필드 `4f34057d9d9e792c28ba18ecae378e98`에 `Stanleigh Stooke`에 대한 다음 [!DNL CRM ID]을(를) 추가합니다.

**결과:** 개인화된 *Luma - 플래티넘 상태 - 환영* 이메일을 수신해야 합니다.

이메일은 다음과 같아야 합니다.

![Luma - 상태 업그레이드 - 환영 이메일](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB 작업 확인]

다음은 세그먼트가 어떻게 표시되어야 하는지를 나타냅니다.

![Luma - 플래티넘 상태 - 세그먼트](/)

여정은 다음과 같아야 합니다.

![플래티넘-상태-업그레이드-여정](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
