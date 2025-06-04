---
title: 코드 기반 경험 채널 만들기
description: AJO의 채널 구성은 오퍼와 같은 개인화된 콘텐츠가 웹, 이메일, 모바일 앱 또는 기타 디지털 터치포인트와 같은 특정 채널을 통해 제공되는 방식을 정의합니다.
role: User
feature: Decisioning
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: a7247b19-877b-4f62-b4d1-1c3a762b3433
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 0%

---

# 코드 기반 경험 채널 만들기

Adobe Journey Optimizer(AJO) [!UICONTROL Decisioning]의 코드 기반 환경은 클라이언트측 JavaScript을 사용하여 개인화된 오퍼를 웹 페이지로 직접 전달할 수 있는 구성입니다. 이 접근 방식을 사용하면 미리 정의된 템플릿이나 시각적 레이아웃 도구에 의존하는 대신 Adobe Web SDK(`Alloy.js`)를 사용하여 오퍼를 렌더링하는 시기와 위치를 개발자가 완벽하게 제어할 수 있습니다.

![채널 만들기](assets/cbe-channel.png)
