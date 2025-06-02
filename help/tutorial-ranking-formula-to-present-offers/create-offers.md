---
title: 우편 번호 타깃팅을 사용하여 위치 기반 오퍼 만들기
description: 의사 결정의 오퍼 항목은 정의된 규칙 및 조건에 따라 사용자에게 전달할 수 있는 메시지, 이미지, 프로모션 또는 추천과 같은 개인화된 단일 콘텐츠 조각을 나타냅니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
exl-id: 7dd49746-bea6-4679-9d88-d8f9d2aa5b52
source-git-commit: fb0ef6d502c6e3ba37ef528683a8888ed83f2990
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# 우편 번호 타깃팅을 사용하여 위치 기반 오퍼 만들기

오퍼를 만들기 전에 오퍼 항목 스키마를 새 필드인 zipcode를 포함하도록 확장했습니다. 이 사용자 정의 필드를 사용하면 각 오퍼에 대상 우편 번호를 명시적으로 태그 지정할 수 있으므로 의사 결정 중에 위치 기반 필터링 및 등급을 사용할 수 있습니다.

스키마가 업데이트되면서 두 개의 개인화된 오퍼가 만들어졌습니다.

* 오퍼 1: &quot;Mira Mesa(92126)를 위한 유연한 투자 계획&quot;
92126 청년 전문직 및 기술 중심 주민을 위한 맞춤형 오퍼로, 장기적 성장을 목표로 하는 상장지수펀드(ETF), 뮤추얼펀드 등 유연한 투자 옵션을 추진한다. Zipcode 필드가 92126으로 설정되어 있습니다.

* 오퍼 2: &quot;Rancho Bernardo (92128) 용 하이일드 CD&quot;
92128년 재무적으로 안정되고 은퇴에 대비한 개인을 대상으로 한 이번 오퍼는 수익률이 보장된 고수익 양도성예금증서(CD)가 특징이다. Zipcode 필드가 92128으로 설정되어 있습니다.

이러한 오퍼는 이제 위치 메타데이터로 보강되어 이후 단계에서 사용자 프로필 ZIP 코드를 기반으로 동적 선택 및 순위를 지정할 수 있습니다.

다음 스크린샷은 오퍼 항목 스키마에 추가된 사용자 지정 속성을 보여 줍니다.

![오퍼 메타데이터](assets/offers-meta-data.png)


## 92126 오퍼

우편 번호92126 오퍼에 대한 오퍼 텍스트

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #f9f9f9; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Boost Your Financial Game with Smart Investment Options   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     In Mira Mesa (92126), ambition meets opportunity. Whether you're building wealth or just getting started, our     <strong>diversified investment plans</strong> — including <strong>tech-focused ETFs</strong> and     <strong>flexible mutual funds</strong> — are designed to grow with your goals.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Enjoy expert guidance, low fees, and strategies built for busy professionals who want more from their money — without the hassle.   </p>   <a href="#start-investing" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Start Investing Smarter   </a> </div>
```


## 92128 오퍼

우편 번호92128 오퍼에 대한 오퍼 텍스트

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #fdfdfd; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Grow Your Savings with Confidence – Exclusive CD Rates for 92128   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Live in Rancho Bernardo? Take advantage of your financial momentum with our <strong>high-yield Certificates of Deposit</strong>, offering up to <strong>5.25% APY</strong>.     Designed for peace of mind and smart growth, our flexible CD options let you lock in guaranteed returns while enjoying the stability you deserve.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Whether you're planning retirement or simply securing your future, this offer is tailored for residents like you.   </p>   <a href="#explore-cd-options" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Explore CD Options   </a> </div>
```

## 일반 오퍼(대체 오퍼)

오퍼와 연결된 우편 번호가 없는 일반 오퍼의 오퍼 텍스트

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #ffffff; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">
  <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">
    Invest Smarter: Build Wealth with Flexible Financial Plans
  </h2>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Looking to take control of your financial future? Our flexible investment solutions are designed to meet a wide range of goals — from growing savings to planning for retirement.
    Choose from diversified mutual funds, ETFs, and professionally managed portfolios, all with expert guidance and minimal hassle.
  </p>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Whether just starting out or optimizing an existing strategy, this offer provides the tools to invest with confidence — no matter where you live.
  </p>
  <a href="#explore-investment-plans" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
    Explore Investment Plans
  </a>
</div>
```

**수입 관련 오퍼**&#x200B;라는 컬렉션에서 이 오퍼들을 그룹화합니다.

오퍼는 모든 방문자가 사용할 수 있습니다. 즉, 엄격한 자격 제한이 없습니다. 그러면 순위 공식이 프로필 컨텍스트를 기반으로 표시할 오퍼를 결정하는 데 중요해집니다.
자격 규칙이 오퍼를 필터링하지 않으므로 세 가지 모두 후보로 처리됩니다.
선택 전략은 세 가지 모두를 검색합니다.
순위 공식은 프로필 속성(예: 우편 번호 및 annualIncome)에 따라 점수를 매겨 가장 적합한 속성을 선택합니다.
