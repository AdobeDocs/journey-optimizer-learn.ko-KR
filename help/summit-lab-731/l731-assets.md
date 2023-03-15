---
title: L731 치트 시트
description: 이 페이지에는 L731 Summit Lab에서 사용하는 텍스트와 링크가 있습니다.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: 8e9f7460410a117031598096d81eabd3090647af
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 39%

---

# Summit Lab L731 - 치트 시트

이 페이지에는 L731 Summit Lab에서 사용하는 텍스트와 링크가 있습니다. 콘텐츠를 복사하여 Journey Optimizer 메시지에 붙여 넣을 수 있습니다.

## 연습 1.1 - 앱 다운로드 및 설치

QR 코드를 스캔하여 앱을 다운로드합니다

>[!BEGINTABS]

>[!TAB iOS]

![iOS용 QR 코드](/help/assets/lab731-ios-qr-code.png)

Testflight를 설치하라는 메시지가 표시됩니다. Testflight를 설치한 후에는 다음 단계에 따라 Vegas Stay 앱을 설치하십시오.

![iOS 설치 단계](/help/assets/lab731-install-ios.png)

>[!TAB Android™]

![Android용 QR 코드](/help/assets/lab731-android-qr-code.png)

Android 시뮬레이터를 사용하는 경우 이 링크를 사용하십시오. [https://ajolab.s3.amazonaws.com/ajolabapp-release.apk](https://ajolab.s3.amazonaws.com/ajolabapp-release.apk)

앱이 Google Play Store에 등록되어 있지 않으므로 경고 메시지가 표시됩니다.

![Android 경고 화면](/help/assets/lab731-install-android.png)

클릭 **설치**

>[!ENDTABS]

## 연습 1.3: Adobe Journey Optimizer에 로그인

[Journey Optimizer에 로그인하려면 여기를 클릭하십시오.](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**로그인 세부 정보:**

* **사용자 이름:** `L731+<your seat number>@summitlab.us` (예: L731+001@summitlab.us)
* **암호:** Adobe2023!


## 연습 2.1 인앱 캠페인 만들기

| 필드 | 텍스트 | 링크 |
|----|----|----|
| 캠페인 이름 | `<your seat number> March Vegas Campaign` |  |
| Matcher | 부유 |  |
| 미디어 URL 옵션 |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| Title | 지금 벌어지고 있습니다. |  |
| 본문 | Adobe Summit이 2023년 3월 21~23일 라스베이거스로 돌아옵니다. 긍정적인 자극이 될 발제자, 스킬을 키울 수 있는 세션, 새로운 인맥을 만나 볼 준비를 하세요. |  |
| 버튼 | 지금 호텔 예약하고 10% 할인 받기 | lab://booking?suite=presidential&amp;discount=10 |
| 단추: 대화형 이벤트 | 인앱 CTA |  |
| 기본 URL |  | iOS: lab:// <br>Android™: https://lab |


## 3단원 옴니채널 여정 만들기

>[!BEGINTABS]

>[!TAB 푸시 메시지]

**Title:**\
베가스 스테이에 오신 것을 환영합니다!

**본문:**\
줄 설 필요 없이 모바일 앱으로 체크인하기

**딥 링크:** lab://checkin

**미디어:**

https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/vegas_online_check_in.jpg?lang=en


푸시 알림에 사용하는 이미지입니다.

![온라인 체크인](/help/assets/vegas_online_check_in.jpg)

>[!TAB SMS 메시지]

**메시지:**
베가스 스테이에 오신 것을 환영합니다 줄 설 필요 없이 모바일 앱으로 체크인하기: lab://checkin

>[!TAB 이메일 메시지]

**제목 줄:**
{{profile.person.name.firstName}}체크인하셨으니, 이제 저희 오퍼에서 고객님께서 머무르실 수 있도록 해주시기 바랍니다!

>[!ENDTABS]
