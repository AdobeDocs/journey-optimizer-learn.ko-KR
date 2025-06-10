---
title: Web SDK을 사용하여 Adobe Journey Optimizer에서 실시간 날씨 데이터로 오퍼 개인화
description: '이 자습서에서는 실시간 컨텍스트 데이터와 Adobe Web SDK Personalization API를 사용하여 Adobe Journey Optimizer에서 동적 날씨 인식 오퍼를 제공하는 방법을 보여줍니다. 웹 사이트의 날씨 속성(예: 온도 및 조건)을 Adobe Experience Platform에 전달하고, 이벤트 스키마에 매핑하며, 의사 결정 규칙 및 등급 공식에 사용하여 페이지 로드 시 오퍼를 개인화하는 방법을 알아봅니다. 실시간 환경 컨텍스트를 통해 디지털 경험을 향상하고자 하는 마케터와 개발자에게 이상적입니다.'
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# 사용 사례 설명

Adobe Journey Optimizer(AJO)의 날씨 관련 데이터를 사용하여 서비스를 제공하면 기업이 실제 실시간 환경 조건을 기반으로 고객 경험을 개인화할 수 있습니다. 날씨는 강력한 상황적 신호입니다. 날씨에 따라 사람들의 요구와 행동이 달라진다. 날씨 데이터를 사용하여:

고객 기분과 환경에 맞는 적절한 오퍼 제공

더운 날, 차가운 음료 또는 AC 장치에 대한 오퍼를 표시하십시오. 비 오는 날에는 잭이나 우산을 홍보하세요

날씨 기반 오퍼의 예


![날씨 오퍼](assets/offers-use-case.png)



## 이 자습서의 사전 요구 사항

* Experience Platform 액세스

* Adobe Experience Platform 태그에 대한 기본 이해

* Experience Platform 개념(프로필, 대상, 데이터 세트)에 대한 기본 이해

* Journey Optimizer 친숙도

* 기본 JavaScript 지식(간단한 기능 읽기 및 쓰기)

* 브라우저 개발 도구 사용 기능(콘솔 및 네트워크 탭)
