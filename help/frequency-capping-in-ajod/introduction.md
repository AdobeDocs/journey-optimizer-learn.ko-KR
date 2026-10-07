---
title: AJO Decisioning을 통해 제공된 Adobe Journey Optimizer(AJO) 오퍼에서 빈도 제한 구현
description: 이 자습서에서는 AJO Decisioning을 사용하여 제공되는 오퍼에 대한 빈도 제한을 활성화하여 기존 Adobe Journey Optimizer(AJO) 구현을 확장합니다. 빈도 상한에 사용되는 노출 및 상호 작용 이벤트를 캡처하는 방법을 간략하게 설명합니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
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
source-wordcount: '214'
ht-degree: 7%
---
# AJO Decisioning을 통해 제공된 Adobe Journey Optimizer(AJO) 오퍼에서 빈도 제한 구현

이 튜토리얼에서는 Adobe Journey Optimizer의 오퍼에 빈도 제한을 적용하여 사용자가 시간이 지남에 따라 동일한 오퍼를 보는 빈도를 제어하는 방법을 보여 줍니다.

이 튜토리얼에서는 날씨 조건에 따라 오퍼를 개인화하는 [튜토리얼](https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction)에 따라 이미 AJO 캠페인을 설정했다고 가정합니다.

Adobe Journey Optimizer은 Adobe Web SDK을 통해 decisioning.propositionDisplay 및 decisioning.propositionInteract 이벤트를 캡처하고 Adobe Experience Platform(AEP)의 XDM 스키마에 매핑함으로써 오퍼 노출 횟수 및 상호 작용을 정확하게 추적할 수 있으므로 오퍼가 사용자에게 표시되는 빈도를 제한할 수 있습니다.

## 이 자습서의 사전 요구 사항

계속하기 전에 웹 표면에 오퍼를 제공하는 Decisioning을 사용하여 유효한 Adobe Journey Optimizer 캠페인이 있는지 확인하십시오.

이 자습서에서는 오퍼 게재가 이미 작동하고 있으며 빈도 제한 동작을 구성하고 확인하는 데만 중점을 두고 있다고 가정합니다.




