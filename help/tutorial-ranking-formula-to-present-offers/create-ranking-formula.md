---
title: 순위 공식 만들기
description: Adobe Journey Optimizer의 순위 공식은 Offer Decisioning 중에 사용되며, 특히 적격 오퍼의 우선 순위를 결정하기 위한 선택 전략 내에서 사용됩니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: eee1b86e-b33f-408e-9faf-90317bc5e861
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# 순위 공식 만들기

Adobe Journey Optimizer의 순위 공식은 Offer Decisioning 중에 사용되며, 특히 적격 오퍼의 우선 순위를 결정하기 위한 선택 전략 내에서 사용됩니다. 여러 오퍼가 주어진 프로필에 적합하지만 비즈니스 논리 또는 프로필 컨텍스트를 기반으로 최상위 오퍼(또는 일부)만 표시되어야 하는 경우 자격 필터링 후에 순위 공식이 적용됩니다.

* Journey Optimizer에 로그인

* 의사 결정 ->전략 설정 ->등급 수식 ->수식 만들기

순위 공식
![이름_설명](assets/formuala-ranking.png)

등급 공식의 기준은 오퍼에 점수를 할당하는 데 사용되는 조건부 규칙을 나타냅니다. 이러한 기준은 오퍼와 프로필 또는 컨텍스트의 속성을 비교하여 특정 개인에 대한 오퍼의 관련성을 결정합니다.



기준 1

이 조건은 &quot;IncomeLevel&quot;로 태그가 지정된 오퍼만 포함하도록 **결정 항목(오퍼)을 필터링합니다**.
그런 다음 필터링된 오퍼는 정의한 추가 논리에 따라 순위 또는 게재와 같은 다음 단계로 진행합니다.
![criteria_one](assets/income-related-formula.png)


다음 표현식은 등급 점수를 만드는 데 사용됩니다

```pql
if(   offer._techmarketingdemos.offerDetails.zipCode = _techmarketingdemos.zipCode,   _techmarketingdemos.annualIncome / 1000 + 10000,   if(     not offer._techmarketingdemos.offerDetails.zipCode,     _techmarketingdemos.annualIncome / 1000,     -9999   ) )
```

공식의 기능

* 오퍼의 우편 번호가 사용자와 동일한 경우, 우선 선택되도록 매우 높은 점수를 제공하십시오.

* 오퍼에 우편 번호가 전혀 없다면(일반 오퍼인 경우) 사용자의 수입을 기준으로 일반 점수를 부여합니다.

* 오퍼에 사용자와 다른 우편 번호가 있는 경우, 오퍼가 선택되지 않도록 매우 낮은 점수를 제공합니다.

이렇게 하면 시스템이

* 항상 먼저 ZIP 일치 오퍼를 표시하려고 합니다.

* 일치하는 항목이 없는 경우 일반 오퍼로 대체되며 다른 우편번호에 해당하는 오퍼를 표시하지 않습니다.


오퍼 항목이 필터 기준을 충족하지 않는 경우(&quot;IncomeLevel&quot; 태그가 없는 경우 등) 오퍼에 기본 순위 점수 10이 부여됩니다.




