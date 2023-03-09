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
source-git-commit: e2312c022f589ebf1218e1767bbc129b57fa1e2a
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 64%

---

# Summit Lab L731 - 치트 시트

이 페이지에는 L731 Summit Lab에서 사용하는 텍스트와 링크가 있습니다. 콘텐츠를 복사하여 Journey Optimizer 메시지에 붙여 넣을 수 있습니다.

## 연습 1.1 - 앱 다운로드 및 설치

### iOS

![iOS용 QR 코드](/help/assets/lab731-ios-qr-code.png)

### Android - 자리 표시자

![Android용 QR 코드](/help/assets/lab731-ios-qr-code.png)


## 연습 1.3: Adobe Journey Optimizer에 로그인

[Journey Optimizer에 로그인하려면 여기를 클릭하십시오.](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**로그인 세부 정보:**

* **사용자 이름:** `L731+<your seat number>@summitlab.us` (예: L731+001@summitlab.us)
* **암호:** Adobe 2023!


## 연습 2.1 인앱 캠페인 만들기



| 필드 | 텍스트 | 링크 |
|----|----|----|
| 캠페인 이름 | `<your seat number> March Vegas Campaign` |  |
| 적절한 항목 | 바보 |  |
| 미디어 URL 옵션 |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| Title | Summit이 라이브로 찾아옵니다! |  |
| 본문 | Adobe Summit이 2023년 3월 21~23일 라스베이거스로 돌아옵니다. 긍정적인 자극이 될 발제자, 스킬을 키울 수 있는 세션, 새로운 인맥을 만나 볼 준비를 하세요. |  |
| 버튼 | 지금 호텔 예약하고 10% 할인 받기 | lab://booking?suite=presidential&amp;discount=10 |
| 단추: 대화형 이벤트 | 인앱 CTA |  |
| 기본 URL |  | iOS: lab:// <br>Android: https://lab |



## 3단원 옴니채널 여정 만들기

| 메시지 | 제목/제목 줄 | 텍스트 | 링크 |
|----|----|----|----|----|
| 푸시 | Vegas Stay에 오신 것을 환영합니다! | 줄 설 필요 없이 모바일 앱으로 체크인하기 | lab://checkin |  |
| SMS |  | Vegas Stay에 오신 것을 환영합니다. 줄 설 필요 없이 모바일 앱으로 체크인하기: lab://checkin |  |
| 이메일 | {{profile.person.name.firstName}}, 체크인되었습니다. 이제 숙박에 대한 오퍼를 확인하십시오! |  |  |


SMS 및 푸시 알림에 사용하는 이미지입니다.

![온라인 체크인](/help/assets/vegas_online_check_in.jpg)
