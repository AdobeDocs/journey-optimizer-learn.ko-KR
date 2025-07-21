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
exl-id: 609a5ddf-d6c6-4f19-bd7f-bca8c266b759
source-git-commit: 9c11ebd2e52de18792e9fa135db955eeeb243673
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# 솔루션 테스트

솔루션을 완전히 테스트하려면 [weather-offers.html](assets/weather-offers.html) 및 [weather-related-offers-script.js](assets/weather-related-offers-script.js) 파일을 웹 서버나 Github Pages와 같은 공용 호스팅 서비스에서 호스팅해야 합니다. 이는 다음 이유 때문에 필요합니다.
- 브라우저의 지리적 위치 API는 HTTPS 또는 localhost를 통해서만 작동합니다

항목을 정리하고 상대 경로가 올바르게 작동하도록 하려면 솔루션을 호스팅하기 위해 다음 폴더 구조를 사용하는 것이 좋습니다.

![폴더 구조](assets/folder-structure.png)

## 제공된 파일 다운로드

[HTML 파일](assets/weather-offers.html)

[Javascript 파일](assets/weather-related-offers-script.js)


## Javascript 파일에서 표면 URL 업데이트

`weather-related-offers-script.js`을(를) 열고 ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`을(를) 업데이트하되 `yourdomain.com`을(를) HTML 파일이 호스팅되는 실제 도메인으로 바꿉니다.

## Adobe Experience Platform 태그 속성 업데이트

텍스트 편집기에서 weather-offers.html 파일을 열고 스크립트 태그를 이 자습서의 이전 단계에서 만든 Adobe Experience Platform 태그 속성의 스크립트 태그로 바꿉니다. 파일을 저장해야 합니다.

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```



## 웹 페이지의 기능

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

   AJO Decisioning에서 반환된 오퍼를 받습니다.

   HTML 콘텐츠를 디코딩합니다.

   에 오퍼를 동적으로 주입 <div id="offerContainer"> 요소를 생성하지 않습니다.

## 다음 단계

[AJO Decisioning의 영향을 측정하고 보고합니다.](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/reporting-on-ajo-od/introduction)

