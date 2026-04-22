---
title: 사용자 권한 캡처
description: 푸시 알림 수신에 대한 사용자의 동의를 캡처할 웹 페이지를 만듭니다.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# 사용자 권한 캡처

이 웹 페이지는 푸시 알림 수신에 대한 사용자의 동의를 캡처합니다. 브라우저의 알림 API를 사용하여 알림을 활성화하라는 메시지를 표시하고, 수락 시 웹 SDK을 사용하여 Adobe Experience Platform에 푸시 구독을 등록합니다. 이렇게 하면 옵트인 사용자만 Adobe Journey Optimizer의 캠페인 및 여정을 통해 푸시 알림을 받을 수 있습니다.

웹 푸시 알림을 활성화하기 위해 페이지는 먼저 초기화 함수 내에서 fetch(&quot;/config&quot;)를 호출하여 구성 파일을 로드합니다. 이 구성은 Node.js 애플리케이션에서 제공하며 데이터 스트림 ID, 조직 ID, VAPID 공개 키, 앱 ID 및 추적 데이터 세트 ID와 같은 키 값을 포함합니다. 구성이 로드되면 Adobe Web SDK이 초기화되고 푸시 메시지를 지원하도록 서비스 작업자가 등록됩니다. 사용자가 알림 활성화 를 클릭하면 브라우저가 웹 알림 API를 사용하는 사용 권한을 묻는 메시지를 표시합니다. 권한이 부여되면 웹 SDK이 푸시 구독을 Adobe Experience Platform으로 보내고, 사용자는 메시지가 반복되지 않도록 24시간 동안 옵트인으로 표시됩니다. 서버를 시작한 후 [샘플 응용 프로그램](http://localhost:3000/)에 포함된 로컬 웹 페이지 shop-smart.html에서 이 흐름을 시도할 수 있습니다.

![요청 권한](assets/request-notifications.png)

