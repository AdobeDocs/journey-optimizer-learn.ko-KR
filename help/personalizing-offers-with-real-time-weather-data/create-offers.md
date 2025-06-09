---
title: 오퍼를 만들어 동적 의사 결정 및 등급을 테스트합니다.
description: 의사 결정의 오퍼 항목은 정의된 규칙 및 조건에 따라 사용자에게 전달할 수 있는 메시지, 이미지, 프로모션 또는 추천과 같은 개인화된 단일 콘텐츠 조각을 나타냅니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: dac6b373226bd0be2533cf859e4f250018cf568b
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---


# 오퍼를 만들어 동적 의사 결정 및 순위 테스트

이러한 오퍼는 Adobe Web SDK(alloy(&quot;sendEvent&quot;))를 통해 전달되는 실시간 컨텍스트 입력(온도 등)을 기반으로 동적 의사 결정 및 등급을 테스트하도록 설계되었습니다.

오퍼를 만들기 전에 오퍼 항목 스키마를 새 필드 offerText를 포함하도록 확장했습니다

![오퍼 스키마](assets/offer-schema.png).

다음 3개의 오퍼 만들기


## Hot Weather 오퍼(태그:hot)

더운 날씨에 대한 오퍼 텍스트

```html
<div data-tags="weather hot skincare sunscreen" style="border: 1px solid #e0e0e0; padding: 1.5rem; border-radius: 10px; background-color: #fff3e0;">   <h2 style="color: #e65100;">Protect Your Skin This Summer</h2>   <p>High temperatures mean high UV risk. Get <strong>20% off</strong> our dermatologist-recommended sunscreens and skin protection kits.</p>   <p>Offer valid this week only for areas with temperatures over 90°F.</p>   <a href="#" style="display:inline-block; margin-top:1rem; padding:0.75rem 1.5rem; background:#e65100; color:white; border-radius:5px; text-decoration:none;">Shop Sunscreen</a> </div>
```


## 온화한 날씨 오퍼(태그:봄)

온화한 날씨에 대한 오퍼 텍스트

```html
<div data-tags="ajo offer-mild-weather">   <h2 style="color: #2e7d32;">🌤️ Enjoy the Outdoors — Gear Up Now!</h2>   <p style="font-size: 1.1rem;">Perfect weather to be outside! Check out our selection of <strong>picnic sets, walking shoes, and fitness accessories</strong> for your next outdoor adventure.</p>   <p style="font-size: 1.1rem;">Get <strong>free shipping</strong> on all outdoor gear this week.</p>   <a href="#" style="display:inline-block;padding:0.75rem 1.5rem;background:#2e7d32;color:white;border-radius:6px;text-decoration:none;margin-top:1rem;">Explore Outdoor Picks</a> </div>
```

## Cold Weather 오퍼(태그:cold)

추운 날씨 오퍼에 대한 오퍼 텍스트

```html
<div class="offer-content" style="text-align: center; padding: 1rem;">   <img src="https://raw.githubusercontent.com/gbedekar489/gbedekar489.github.io/main/weather/pexels-romanp-16170.jpg"         alt="Winter clothing"         style="width: 100%; max-width: 400px; border-radius: 12px; margin-bottom: 1rem;">   <h2>Cold Weather, Hot Deals 🧤</h2>   <p>Stay warm in style with our exclusive <strong>25% off</strong> winter outerwear. From puffer jackets to wool scarves, find the perfect layers to beat the chill.</p>   <p><strong>Use code:</strong> <code>WINTER25</code> at checkout</p>   <p><em>Limited time offer. While supplies last.</em></p> </div>
```

### 컬렉션 만들기

Decisioning -> Catalogs ->Collection->Create collection으로 이동합니다.
컬렉션 이름을 **날씨 관련 오퍼**&#x200B;로 지정합니다.

규칙 빌더를 사용하여 이 컬렉션에서 이러한 오퍼를 그룹화합니다.

