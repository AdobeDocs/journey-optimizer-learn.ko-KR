---
title: Decisioning을 사용하여 웹 오퍼 개인화
description: Journey Optimizer(AJO) Decisioning을 사용하여 Experience Platform(AEP)에 내장된 대상 세분화를 활용하여 웹 페이지에 개인화된 오퍼를 제공하는 방법을 알아봅니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
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
source-wordcount: '239'
ht-degree: 7%
---
# Decisioning을 사용하여 웹 오퍼 개인화

이 자습서는 Adobe Experience Platform(AEP) Web SDK을 사용하여 이전에 만든 대상 세분화 설정을 기반으로 합니다. [이전 자습서](https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction)에서는 주식, 채권 또는 예금 증서(CD)에 대한 관심도와 같은 사용자 환경 설정을 캡처하여 개인을 Experience Platform 내의 타깃팅된 대상으로 세그먼트화하는 데 사용했습니다. 이 튜토리얼은 Adobe Journey Optimizer(AJO) Decisioning을 사용하여 해당 대상자에게 실시간으로 개인화된 금융 오퍼를 전달하여 참여 및 전환 결과를 모두 향상시킴으로써 그러한 기반을 기반으로 합니다.


## 이 자습서의 사전 요구 사항

* Experience Platform 액세스

* Experience Platform 개념(프로필, 대상, 데이터 세트)에 대한 기본 이해

* Journey Optimizer 친숙도

* 기본 JavaScript 지식(간단한 기능 읽기 및 쓰기)

* 브라우저 개발 도구 사용 기능(콘솔 및 네트워크 탭)


## 목표

이 튜토리얼에서는 Journey Optimizer을 사용하는 웹 사이트에서 주식, 채권 또는 CD와 같은 개인화된 투자 오퍼를 제공하는 방법을 안내합니다. 대상자 세분화 및 의사 결정 전략을 활용하여 각 방문자의 환경 설정을 기반으로 가장 관련성이 높은 오퍼가 표시되도록 하는 방법을 알아봅니다.

## 사용된 도구

* Adobe Experience Platform(AEP)
* Adobe Journey Optimizer (AJO)
* Adobe Experience Platform 태그
* AEP 웹 SDK(`Alloy.js`)
* AEP Edge 세그멘테이션
* 오퍼를 표시하는 웹 페이지
