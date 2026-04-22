---
title: 대상자 만들기
description: 푸시 알림을 수신할 자격이 있는 사용자를 타겟팅하는 Adobe Experience Platform의 세그먼트를 정의합니다.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 3%

---

# 대상자 만들기

캠페인에 대한 대상을 만들려면 푸시 알림을 받을 수 있는 사용자를 타겟팅하는 세그먼트를 Adobe Experience Platform에서 정의합니다. 이 자습서에서는 활성 푸시 구독(푸시 토큰이 있음)이 있고, 알림을 옵트아웃하지 않았으며(차단 목록 플래그가 false임), 지정된 구성과 연결되어 있습니다(응용 프로그램 식별자가 `my-first-push`과(와) 같음). 이러한 사용자는 Adobe Journey Optimizer의 캠페인이나 여정을 통해 웹 푸시 알림을 받을 수 있습니다. 대상자를 만든 후 프로필이 채워지고 타깃팅할 준비가 되도록 평가되었는지 확인하십시오.
그런 다음 이 대상자는 캠페인에서 구독된 사용자에게만 예약된 웹 푸시 메시지를 전달하는 데 사용됩니다.

![create-audience](assets/push-audience.png)

