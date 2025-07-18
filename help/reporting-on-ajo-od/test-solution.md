---
title: 솔루션 테스트
description: 노출을 캡처하고 오퍼에서 이벤트를 클릭할 간단한 웹 페이지를 만듭니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# 솔루션 테스트

솔루션을 완전히 테스트하려면 [weather-offers.html](assets/weather-offers.html) 및 [capture-impressions-click-events.js](assets/capture-impressions-click-events.js) 파일을 웹 서버나 Github Pages와 같은 공용 호스팅 서비스에서 호스팅해야 합니다. 브라우저의 지리적 위치 API는 HTTPS 또는 localhost를 통해서만 작동하므로 필요합니다

## 제공된 파일 다운로드

[HTML 파일](assets/weather-offers.html)

[Javascript 파일](assets/capture-impressions-click-events.js)

## Javascript 파일에서 표면 URL 업데이트

`capture-impressions-click-events.js`을(를) 열고 ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`을(를) HTML 파일이 호스팅된 실제 도메인으로 바꾸어 `yourdomain.com`을(를) 업데이트합니다.


## Adobe Experience Platform 태그 속성 업데이트

텍스트 편집기에서 weather-offers.html 파일을 열고 스크립트 태그를 이 자습서의 이전 단계에서 만든 Adobe Experience Platform 태그 속성의 스크립트 태그로 바꿉니다. 파일을 저장해야 합니다.

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## 오퍼와 상호 작용

- 즐겨 찾는 브라우저에서 웹 페이지를 엽니다.

- _&#x200B;**위치 추적**&#x200B;_ 허용 위치를 기반으로 날씨 세부 정보를 가져오는 데 필요합니다.

- 오퍼에서 버튼을 클릭하여 상호 작용 이벤트를 트리거합니다.

## 보고서 보기

- Journey Optimizer에 로그인

- 여정 관리 ->캠페인으로 이동합니다.

- 캠페인을 클릭한 다음 보고서 메뉴에서 적절한 보고서를 선택합니다.
