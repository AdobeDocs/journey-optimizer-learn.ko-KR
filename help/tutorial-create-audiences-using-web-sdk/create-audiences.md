---
title: Adobe Journey Optimizer에서 대상 만들기
description: AJO에서 타겟팅된 대상을 정의하고 구축하여 개인화된 고객 여정 및 실시간 의사 결정을 수행하는 방법을 알아봅니다
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: d90f1868-0514-49b2-832d-82460883b6e4
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%
---
# Adobe Journey Optimizer에서 대상 만들기


Adobe Experience Platform의 대상은 개인화된 경험을 제공하기 위해 작업, 환경 설정 또는 프로필 정보를 기반으로 만들어진 사용자 그룹입니다.

* Journey Optimizer에 로그인
* 고객 -> 대상 ->대상 만들기 로 이동합니다.
* 규칙 작성 방법을 사용하여 대상 만들기

  ![대상자](assets/rule-based-audience.png)

* 다음 3개의 대상 만들기

  * 주식에 관심이 있는 고객

  * 채권에 관심이 있는 고객

  * CD에 관심이 있는 고객


* 실시간 자격을 얻으려면 각 대상의 평가 방법이 _&#x200B;**Edge**&#x200B;_(으)로 설정되어 있는지 확인하십시오.
  ![edge-audience](assets/audience-edge.png)

* PreferredFinancialInstrument 필드를 사용하여 선택한 투자 이익(예: 주식, 채권 또는 CD)을 기준으로 사용자를 세그먼트화합니다

![이벤트](assets/event-attribute.png)

![PreferredFinancialInstrument](assets/stock-customers.png)




>[!NOTE]
>
>&#x200B;>이벤트 탭에 PreferredFinancialInstrument 필드가 표시되지 않으면 설정 아이콘을 클릭하고 전체 XDM 스키마 표시 를 토글합니다.



![toggle-full-xdm-schema](assets/show-custom-fields.png)
