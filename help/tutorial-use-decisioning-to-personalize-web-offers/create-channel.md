---
title: 코드 기반 경험 채널 만들기
description: AJO의 채널 구성은 오퍼와 같은 개인화된 콘텐츠가 웹, 이메일, 모바일 앱 또는 기타 디지털 터치포인트와 같은 특정 채널을 통해 제공되는 방식을 정의합니다.
role: User
feature: Decisioning
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: a7247b19-877b-4f62-b4d1-1c3a762b3433
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%
---
# 코드 기반 경험 채널 만들기

Adobe Journey Optimizer(AJO) [!UICONTROL Decisioning]의 코드 기반 환경은 클라이언트측 JavaScript을 사용하여 개인화된 오퍼를 웹 페이지로 직접 전달할 수 있는 구성입니다. 이 접근 방식을 사용하면 미리 정의된 템플릿이나 시각적 레이아웃 도구에 의존하는 대신 Adobe Web SDK(`Alloy.js`)를 사용하여 오퍼를 렌더링하는 시기와 위치를 개발자가 완벽하게 제어할 수 있습니다.

![채널 만들기](assets/cbe-channel.png)
