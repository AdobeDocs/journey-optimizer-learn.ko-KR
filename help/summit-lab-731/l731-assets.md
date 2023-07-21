---
title: L731 컨닝 페이퍼
description: 이 페이지에는 L731 Summit Lab에서 사용하는 텍스트와 링크가 있습니다.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: 2f0412400db4d5bdddbb84d41e8bde17ea2533b2
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 66%

---

# Summit Lab L731 - 컨닝 페이퍼

이 페이지에는 L731 Summit Lab에서 사용하는 텍스트와 링크가 있습니다. 콘텐츠를 복사하여 Journey Optimizer 메시지에 붙여 넣을 수 있습니다.

## 연습 1.1 - 앱 다운로드 및 설치

QR 코드를 스캔하여 앱을 다운로드합니다.

>[!BEGINTABS]

>[!TAB iOS]

![iOS용 QR 코드](/help/assets/lab731-ios-qr-code.png)

>[!IMPORTANT]
>
>사용 코드를 요청하는 경우 TestFlight 앱을 닫고 QR 코드를 다시 스캔하십시오.
>
>알림을 허용하십시오.
>

Testflight를 설치하라는 메시지가 표시됩니다(1~4단계). Testflight를 설치한 후 5~8단계에 따라 Vegas Stay 앱을 설치합니다.

<table>
<tr>
</tr>
<tr>
<td>
 <div>
      <p>
      <b>1단계 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-1.png"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>2단계 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-2.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>3단계 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-3.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>4단계 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-4.PNG"/>
      </a>
      </div>
  </td>
  </tr>
  <tr>
<td>
 <div>
      <p>
      <b>5단계 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-5.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>6단계 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>7단계 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>8단계 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-8.PNG"/>
      </a>
      </div>
  </td>
  </tr>
</table>

>[!TAB Android]

![Android용 QR 코드](/help/assets/lab731-android-qr-code.png)

앱이 Google Play Store에 등록되어 있지 않으므로 경고 메시지가 표시됩니다.

![Android 경고 화면](/help/assets/lab731-install-android.png)

**무시하고 설치**&#x200B;를 클릭합니다

>[!ENDTABS]

## 연습 1: Adobe Journey Optimizer에 로그인하기

[Journey Optimizer에 로그인하려면 여기를 클릭하십시오](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home){target="_blank"}

**로그인 세부 정보:**

* **사용자 이름:** `L731+<your seat number>@summitlab.us` (예: L731+001@summitlab.us)
* **암호:** Adobe2023!


## 연습 2 인앱 캠페인 만들기

| 섹션 | 필드 | 텍스트 | 링크 |
|----|----|----|----|
| **속성** | 캠페인 이름 | `<your seat number> Vegas Stay Campaign` |  |
| **트리거** | 주/도 | 지금 예약하기 |  |
| **콘텐츠 편집:** 미디어 | 미디어 URL 옵션 |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| **콘텐츠 편집:** 콘텐츠 | Title | 할인 혜택을 받으세요! |  |
| **콘텐츠 편집:** 콘텐츠 | 본문 | Adobe 맥스가 라스베이거스로 돌아온다. 긍정적인 자극이 될 발제자, 스킬을 키울 수 있는 세션, 새로운 인맥을 만나 볼 준비를 하세요. 지금 스위트룸을 예약하고 10% 할인을 받으세요. |  |
| **콘텐츠 편집:** 단추 | 버튼 | 10% 할인을 받으세요! | lab://booking?suite=presidential&amp;discount=10 |
| **콘텐츠 편집:** 단추 | 이벤트 상호 작용 | 인앱 CTA |  |
| **장치에서 미리 보기** |  | 장치에서 미리 보기에 사용할 기본 URL |  | **iOS:** lab:// <br>**Android**: https://lab |

## 연습 3: 푸시 알림 만들기

| 필드 | 텍스트 | 링크 |
|----|----|----|
| 캠페인 이름 | `<your seat number> Max Push Campaign` |  |
| Title | 이봐! |  |
| 본문 | Adobe 맥스가 베가스로 돌아온다는 거 알고 있었어? 지금 객실을 예약하고 10% 할인을 받으세요. |  |
| 미디어 URL 옵션 |  | https://i.ibb.co/1M0BnZn/Firefly-Big-conference-big-stage-with-ADBE-text-on-screen-40178.jpg |
