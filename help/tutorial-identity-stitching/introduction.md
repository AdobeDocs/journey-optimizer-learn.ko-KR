---
title: AEP의 ID 결합
description: Adobe Journey Optimizer(AJO)의 실시간 개인화 및 오퍼 결정을 위한 통합 프로필을 제공하여 알려진 사용자(CRMID)와 익명의 웹 방문자(ECID) 간의 ID 결합을 설정합니다.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 11%
---
# AEP의 ID 결합

최신 고객 경험에서 디바이스 및 채널 간에 사용자 ID를 통합하는 것은 중요합니다. 이 사용 사례에서는 알려진 CRM ID(사용자 로그인 동안 캡처됨)를 Adobe Experience Platform 웹 AEP에서 생성한 익명의 Experience Cloud ID(ECID)와 연결하여 Adobe(SDK)에서 ID 결합을 구현하는 방법을 보여 줍니다. AEP은 이러한 ID를 실시간으로 결합함으로써 익명 동작과 인증된 데이터를 모두 아우르는 보다 완벽한 고객 프로필을 구축할 수 있습니다. 이를 통해 Adobe Journey Optimizer(AJO)과 같은 도구 내에서 보다 정확한 대상 세분화, 개인화 및 의사 결정을 수행할 수 있습니다.

## ID 결합 자습서에 필요한 기술

이 자습서를 최대한 활용하려면 다음을 잘 알고 있는 것이 좋습니다.

- **Adobe Experience Platform(AEP) 핵심 개념**\
  스키마, 데이터 세트, ID, 병합 정책 및 실시간 프로필에 대한 이해.

- **스키마 및 ID 모델링**\
  프로필 및 이벤트 기반 스키마에서 ID 필드를 구성하는 기능.

- **Adobe 시작(태그) 및 웹 SDK(Alloy.js)**\
  웹 SDK을 사용하여 AEP으로 데이터를 전송하기 위한 데이터 요소 및 규칙 설정 관련 경험입니다.

- **JavaScript 기본 사항**\
  사용자 입력을 캡처하고, 이벤트를 트리거하고, API 호출을 디버깅하는 함수를 사용하는 데 익숙합니다.

- **AEP 디버깅 도구**\
  AEP Debugger 및 ID 그래프 뷰어를 사용하여 ID 결합의 유효성을 검사하는 기능.

- **AEP에서 데이터 수집**\
  샘플 데이터를 데이터 세트에 업로드하고 데이터 품질을 보장하는 것에 익숙합니다.


