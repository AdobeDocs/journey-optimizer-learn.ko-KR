---
title: 솔루션 테스트
description: 간단한 웹 페이지를 만들어 실시간 온도 데이터를 사용하여 상황별 오퍼 개인화를 테스트합니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: a9fc14da78e1c67b01aef5dcdd417ce02d36d50a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# 솔루션 테스트

실시간 온도 데이터를 사용하여 상황별 오퍼 개인화를 테스트하기 위해 웹 페이지가 제작되었습니다. 사용자가 페이지를 방문하면 브라우저가 지리적 위치 액세스를 묻는 메시지를 표시합니다. 승인 시 이 페이지는 OpenWeatherMap API를 통해 온도, 조건 및 도시 등 현재 날씨 세부 정보를 가져옵니다. 이 컨텍스트 데이터는 사용자에게 표시되며, Adobe Web SDK(Alloy)를 사용하여 Adobe Experience Platform으로 전송됩니다.

sendEvent 호출은 renderDecisions: false로 구성됩니다. 즉, Adobe Journey Optimizer에서 반환한 오퍼가 수동으로 처리됩니다. 스크립트는 의사 결정 응답을 처리하고, 콘텐츠를 디코딩하고, 가장 관련성이 높은 오퍼를 지정된 컨테이너(#offerContainer)에 동적으로 삽입합니다.

## JavaScript의 기능

JavaScript은 사용자의 위치에 따라 날씨 정보를 동적으로 가져오고 Adobe Experience Platform(AEP)를 사용하여 개인화된 오퍼를 제공합니다. 다음은 단계에 대한 분류입니다.

1. **합금이 로드될 때까지 대기**

   스크립트는 개인화 요청을 수행하기 전에 Adobe Web SDK(Alloy)가 완전히 로드되도록 합니다.

2. **사용자의 위치를 가져옵니다**

   브라우저의 지리적 위치 API를 사용하여 사용자의 현재 위도와 경도를 검색합니다.

3. **날씨 데이터를 가져옵니다**

   최신 날씨 세부 정보를 얻으려면 OpenWeatherMap API를 호출합니다.

   온도(F)

   기상 조건(예: &quot;비&quot;, &quot;쾌청함&quot;)

   도시 이름

   습도

4. **웹 페이지에 날씨 정보 표시**

   다음과 같은 메시지로 DOM을 업데이트합니다.

   &quot;샌디에이고의 현재 기온은 맑은 하늘에 72°F입니다.&quot;

5. **날씨 컨텍스트를 AEP으로 전송**

   alloy(&quot;sendEvent&quot;)를 사용하여 컨텍스트 기반 날씨 데이터를 AEP에 전송

   ```javascript
   xdm: {
   eventType: "decisioning.request",
   _techmarketingdemos: {
   temperature: temp,
   weatherConditions: condition,
   cityName: city
     }
   }
   ```

6. **오퍼 검색 및 렌더링**

   AJO에서 반환된 오퍼를 받습니다.

   HTML 콘텐츠를 디코딩합니다.

   에 오퍼를 동적으로 주입 <div id="offerContainer"> 요소를 생성하지 않습니다.

7. **샘플 Assets**

   솔루션을 테스트하는 데 사용되는 웹 페이지를 다운로드할 수 있습니다

[웹 페이지](assets/weather-offers.html)

[JavaScript 코드](assets/weather-related-offers-script.js)

