---
title: L535 치트 시트
description: 이 페이지에는 L535 Summit Lab에서 사용 중인 텍스트와 링크가 있습니다.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: 1c3f4341-1293-463d-bee0-57440fcff23a
source-git-commit: 1e1878f76315f23882e73470f21d6c3f454aac5b
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 24%

---

# Summit Lab L535 - 치트 시트

이 페이지에는 L535 Summit Lab에서 사용 중인 텍스트와 링크가 있습니다. 콘텐츠를 복사하여 Journey Optimizer 메시지에 붙여 넣을 수 있습니다.

## 링크

* [SecurFinancial 웹 사이트](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U){target="_blank"}
* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys){target="_blank"}
* [L535 통합 문서](/help/summit-lab-assets/assets/summit_lab_manual_l535-final-v4.pdf){target="_blank"}
* [앱 다운로드](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html){target="_blank"}

## 연습용으로 복사 및 붙여넣기

### 연습 2.1 - Journey Optimizer 로그인

다음 세부 정보를 사용하여 로그인합니다.

이메일 주소:    L535+*시트 번호*@adobeeventlab.com

암호:       Adobe4Summit!


### 연습 2.3 - 이메일 메시지 구성

#### 프롬프트

```
Generate a welcome email for new SecurFinancial customers who just opened a new checking account. 
Add a call to action to install the SecurFinancial mobile app.
```

### 연습 3.1 - SMS 메시지에 동적 콘텐츠 적용

#### 코드

```
{%#if select _Push_details1 from profile.pushNotificationDetails where
_Push_details1.token.isNotNull()%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Open the
app
{%else%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Click here
to install the app: https://demo-systemnext.
s3.amazonaws.com/dxdemo/summit/index.html
{%/if%} 
```

### 연습 문제 4.2 - 처리 구성

#### 제목

```
Welcome to SecurFinancial
```

#### 본문 텍스트

```
Did you know you can find an ATM near in the SecurFinancial app? Try it now!
```

#### URL

```
dxdemo://atm
```

### 연습 문제 6 - 콘텐츠 카드

#### 제목

```
Welcome to SecurFinancial!
```

#### 본문

```
Thank you for downloading the app. You can find ATMs, track your spending and more. All within the app.
```

#### 미디어 URL

```
https://demo-system-next.s3.amazonaws.com/assets/securfinancial/home-loan.jpg
```

#### 버튼 제목

```
Find ATMs
```

#### 대상 URL

```
dxdemo://atm
```

## 이미지

![SecureFinancial 로고](/help/summit-lab-assets/assets/SecureFinancial-logo.png)


![휴대폰](/help/summit-lab-assets/assets/online-banking-app-01.png)
