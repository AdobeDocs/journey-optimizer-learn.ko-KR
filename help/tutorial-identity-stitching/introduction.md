---
title: AEP의 ID 결합
description: 알려진 사용자(CRMID)와 익명 웹 방문자(ECID) 간의 ID 결합을 설정하여 Adobe Journey Optimizer(AJO)에서 실시간 개인화 및 오퍼 의사 결정에 통합 프로필을 활성화합니다.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# 사용 사례 설명

최신 고객 경험에서 디바이스 및 채널 간에 사용자 ID를 통합하는 것은 중요합니다. 이 사용 사례에서는 알려진 CRM ID(사용자 로그인 동안 캡처됨)를 Adobe Experience Platform 웹 SDK에서 생성한 익명 Experience Cloud Adobe ID(ECID)와 연결하여 AEP에서 ID 결합을 구현하는 방법을 보여 줍니다. AEP은 이러한 ID를 실시간으로 결합함으로써 익명 동작과 인증된 데이터를 모두 아우르는 보다 완벽한 고객 프로필을 구축할 수 있습니다. 이를 통해 Adobe Journey Optimizer(AJO)과 같은 도구 내에서 보다 정확한 대상 세분화, 개인화 및 의사 결정을 수행할 수 있습니다.

