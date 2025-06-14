---
title: AEP의 ID 결합
description: 알려진 사용자(CRMID)와 익명 웹 방문자(ECID) 간의 ID 결합을 설정하여 Adobe Journey Optimizer(AJO)에서 실시간 개인화 및 오퍼 의사 결정에 통합 프로필을 활성화합니다.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
source-git-commit: f3aeb66ca67448e7751ab2cd6d0bb6ce38f73530
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 0%

---

# AEP의 ID 결합

최신 고객 경험에서 디바이스 및 채널 간에 사용자 ID를 통합하는 것은 중요합니다. 이 사용 사례에서는 알려진 CRM ID(사용자 로그인 동안 캡처됨)를 Adobe Experience Platform 웹 SDK에서 생성한 익명 Experience Cloud Adobe ID(ECID)와 연결하여 AEP에서 ID 결합을 구현하는 방법을 보여 줍니다. AEP은 이러한 ID를 실시간으로 결합함으로써 익명 동작과 인증된 데이터를 모두 아우르는 보다 완벽한 고객 프로필을 구축할 수 있습니다. 이를 통해 Adobe Journey Optimizer(AJO)과 같은 도구 내에서 보다 정확한 대상 세분화, 개인화 및 의사 결정을 수행할 수 있습니다.

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


