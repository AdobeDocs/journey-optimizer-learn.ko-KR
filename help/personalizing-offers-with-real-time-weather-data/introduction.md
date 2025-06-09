---
title: Web SDK을 사용하여 Adobe Journey Optimizer에서 실시간 날씨 데이터로 오퍼 개인화
description: '이 자습서에서는 실시간 컨텍스트 데이터와 Adobe Web SDK Personalization API를 사용하여 Adobe Journey Optimizer에서 동적 날씨 인식 오퍼를 제공하는 방법을 보여줍니다. 웹 사이트의 날씨 속성(예: 온도 및 조건)을 Adobe Experience Platform에 전달하고, 이벤트 스키마에 매핑하며, 의사 결정 규칙 및 등급 공식에 사용하여 페이지 로드 시 오퍼를 개인화하는 방법을 알아봅니다. 실시간 환경 컨텍스트를 통해 디지털 경험을 향상하고자 하는 마케터와 개발자에게 이상적입니다.'
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: d46c5a922b8448f57b8a730188284294c3caba96
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# 사용 사례 설명

Adobe Journey Optimizer(AJO)의 날씨 관련 데이터를 사용하여 서비스를 제공하면 기업이 실제 실시간 환경 조건을 기반으로 고객 경험을 개인화할 수 있습니다. 날씨는 강력한 상황적 신호입니다. 날씨에 따라 사람들의 요구와 행동이 달라진다. 날씨 데이터를 사용하여:

    고객의 기분과 환경에 맞는 적절한 오퍼를 제공합니다.
    
    더운 날 차가운 음료 또는 AC 장치에 대한 제안을 표시합니다. 비 오는 날에는 재킷이나 우산 
을 홍보하세요.
![날씨 오퍼](assets/offers-use-case.png)