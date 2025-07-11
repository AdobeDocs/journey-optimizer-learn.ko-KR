---
title: 우편 번호 및 소득을 기반으로 하는 등급 수식으로 오퍼 개인화
description: 보다 높은 참여도와 보다 스마트한 개인화를 위해 각 사용자의 우편번호 및 수입 수준에 맞게 맞춤화된 가장 관련성이 높은 금융 오퍼를 동적으로 제공하려면 Adobe Journey Optimizer의 등급 공식을 사용하십시오.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-27T00:00:00Z
jira: KT-18188
exl-id: 11685f7c-8048-4318-9c28-71bd7da8f7ff
source-git-commit: 85d3def3afb1d073b133df40e4cbf32d00a3a5c9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# 사용자 우편번호 및 소득을 기반으로 하는 등급 수식으로 오퍼 개인화

이 사용 사례에서는 Adobe Journey Optimizer 내에서 우편 번호 및 연간 소득과 같은 사용자 특성을 활용하여 개인화된 금융 오퍼를 제공하는 방법을 보여 줍니다. 등급 수식을 사용하면 위치별 프로모션 및 소득 기반 자격 조건을 기반으로 오퍼에 지능적으로 점수가 매겨지고 우선 순위가 지정됩니다. 예를 들어 고수익 CD는 부유한 우편번호를 사용하는 사용자에게 홍보할 수 있는 반면, 다양한 투자 옵션은 신흥 투자자에게 표시됩니다. 등급 수식을 사용하면 각 사용자가 관련성이 있고 경제적으로 적절한 오퍼를 받을 수 있습니다. 등급 기준은 프로필 속성, 컨텍스트 신호 및 선택적 AI 모델을 사용하여 정의하여 의사 결정 정밀도를 더욱 향상시킵니다. 오퍼는 웹 또는 이메일 채널을 통해 실시간으로 전달되므로 참여도와 전환율이 높아집니다. 이 접근 방식은 비즈니스 논리와 데이터 기반 개인화를 결합하여 사용자 경험과 마케팅 효과를 향상시킵니다.

## 전제 조건

이 튜토리얼은 주요 Adobe Journey Optimizer 및 Adobe Experience Platform 개념을 기반으로 합니다. 계속하기 전에 다음 전제 조건이 충족되는지 확인하십시오.

* [ID 연결 자습서](https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorial-on-identity-stitching-in-aep/introduction)이(가) 완료되었습니다. CRM ID가 Adobe Experience Platform의 ECID와 연결되어 있습니다.

* 컨텐츠 정의, 메타데이터 설정 및 자격 규칙을 포함하여 AJO에서 오퍼 항목을 생성하는 방법에 익숙합니다.

* 오퍼 전달을 위한 채널(예: 웹 또는 이메일) 구성에 익숙합니다.

* AJO의 캠페인 생성 및 활성화에 익숙합니다.

* Adobe Launch(태그)를 사용하여 웹 SDK을 배포하고 ID 및 프로필 데이터가 포함된 이벤트를 전송하는 방법에 익숙합니다.

이 튜토리얼에서는 offer decisioning의 다음 단계를 다룹니다.

* 우편 번호 및 연간 소득과 같은 프로필 속성을 사용하여 등급 지정 방법 만들기

* 선택 전략을 정의하여 오퍼를 그룹화하고 우선순위를 지정합니다.

* 각 개인에게 가장 적합한 오퍼를 제공하기 위한 의사 결정 정책 구축.
