---
title: Adobe Journey Optimizer에서 JSON 콘텐츠를 사용하여 Personalization 게재
description: Adobe Journey Optimizer(AJO)의 JSON 콘텐츠 유형을 활용하여 유연한 데이터 기반 개인화 경험을 구축합니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-18T00:00:00Z
jira: KT-18387
recommendations: noDisplay, noCatalog
source-git-commit: 9f5b52063605832a9b00c05fb1a93bf60ec7686f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Adobe Journey Optimizer에서 JSON 콘텐츠를 사용하여 Personalization 게재

이 섹션은 프런트엔드에서 오퍼가 렌더링되는 방식을 보다 세밀하게 제어하려는 고급 사용자를 위한 추가 리소스로 제공됩니다.

CBE(코드 기반 경험)에서 JSON 콘텐츠 유형을 사용하면 구조화된 오퍼 데이터를 반환하고 JavaScript을 사용하여 렌더링을 동적으로 처리할 수 있습니다. JSON 콘텐츠 유형은 사용자 지정 레이아웃, 조건부 논리 또는 날씨, 위치 또는 장치 유형과 같은 컨텍스트 데이터와의 통합이 필요한 시나리오에 특히 유용합니다.

기본 오퍼 제공에는 필요하지 않지만, 이 접근 방식은 개발자가 표준 HTML 렌더링의 기능을 넘어서 개인화된 데이터 기반 경험을 구축할 수 있는 유연성을 제공합니다.

## JSON 콘텐츠 유형이 있는 코드 기반 경험(CBE) 만들기 .

먼저 Adobe Journey Optimizer에서 새 CBE(코드 기반 경험)를 만들고 컨텐츠 형식을 JSON으로 설정합니다. 컨텐츠 유형은 AJO에 렌더링된 HTML이 아닌 구조화된 오퍼 데이터(예: offerText, 이미지 또는 메타데이터)를 JSON 개체로 반환하도록 지시합니다. 플랫폼(예: 웹), 오퍼가 표시되는 타겟 URL 및 페이지의 위치(예: offerContainer와 같은 컨테이너 ID)를 정의합니다. 이 구성을 사용하면 웹 애플리케이션이 오퍼 데이터를 수신하고 JavaScript을 사용하여 동적으로 렌더링할 수 있습니다.

![json-content-type](assets/cbe-json-content.png)

## CBE를 캠페인과 의사 결정 정책 연결

JSON 콘텐츠 유형이 있는 코드 기반 경험(CBE)이 만들어지면 의사 결정 정책을 통해 캠페인에 연결됩니다. 의사 결정 정책은 프로필 또는 컨텍스트 데이터를 기반으로 오퍼 자격, 등급 및 게재의 논리를 정의합니다.

Personalization 편집기에 의사 결정 정책(예: 인앱 메시지 또는 이메일의 경우)을 삽입할 때 출력이 유효한 JSON 구조를 유지하는지 확인하는 것이 중요합니다.

캠페인 내의 Personalization 편집기(PE)에 의사 결정 정책을 삽입하면 Adobe Journey Optimizer에서 선택한 정책을 기반으로 Handlebars 루프를 자동으로 생성합니다. 예:
![기본 코드](assets/handlebar-code-default.png)
이 루프는 정책에서 반환된 모든 결정 항목을 반복하고 각 오퍼에서 offerText 필드를 주입합니다. 이 기본 구조는 HTML 콘텐츠 유형에 잘 작동하지만 JSON 콘텐츠로 작업할 때 특히 결과를 프로그래밍 방식으로 구문 분석하는 경우 유효한 JSON 배열 또는 개체를 생성하기 위해 재구성해야 할 수 있습니다.

![재구성된 코드](assets/restructured-code.png)

이 Handlebars 템플릿은 각 오브젝트에 단일 offerText 필드가 포함된 오퍼 오브젝트의 JSON 배열을 출력하도록 설계되었습니다. 지정된 결정 정책에서 반환된 결정 항목을 반복하고 각 offerText를 JSON 오브젝트 형식으로 래핑합니다.

## JSON 오퍼 응답 구문 분석

AJO의 응답에는 `propositions[].items[].data.content[]` 구조 아래에 JSON 형식의 개인화된 결정 항목이 포함되어 있습니다. 각 콘텐츠 항목에는 offerText와 같은 필드가 포함되어 있습니다.

```javascript
(response.propositions || []).forEach(p => {
  (p.items || []).forEach(item => {
    const contents = item.data?.content || [];
    contents.forEach(contentItem => {
      const html = contentItem.offerText || "";
      const wrapper = document.createElement("div");
      wrapper.className = "offer";
      wrapper.innerHTML = html;
      document.getElementById("offerContainer").appendChild(wrapper);
    });
  });
});
```

### 샘플 자산

시작하려면 JSON 기반 오퍼를 사용하고 웹 페이지에서 동적으로 렌더링하는 방법을 보여 주는 샘플 HTML 파일 및 JavaScript 파일을 다운로드합니다.

[JavaScript 코드](assets/weather-related-offers-script-multiple-json.js)
[HTML 파일](assets/multiple-json.html)