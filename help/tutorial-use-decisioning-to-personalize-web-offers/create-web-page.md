---
title: 솔루션을 테스트할 웹 페이지 만들기
description: Decisioning을 사용하여 전달된 개인화된 오퍼를 테스트하는 웹 페이지입니다.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 72a67137-303d-4dfe-9b70-322c81e5fb27
source-git-commit: 2ca9ffee1a2326b8ae55a8e8de496a632fea79c8
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# 솔루션을 테스트할 웹 페이지 만들기

이 웹 페이지는 Adobe Journey Optimizer Decisioning을 통해 제공되는 개인화된 오퍼를 테스트하기 위해 만들어졌습니다. 또한 sendEvent 호출을 트리거하고 반환된 오퍼 컨텐츠를 렌더링할 수 있는 제어된 환경을 제공하여 전체적인 개인화 설정을 확인하고 의사 결정이 예상대로 작동하는지 확인하는 데 도움이 됩니다.

다음 스크립트는 Adobe Journey Optimizer을 사용하여 웹 페이지에서 개인화된 오퍼를 가져오고 표시하는 역할을 합니다.

1. HTML 엔티티 디코딩: 오퍼 컨텐츠에 있는 모든 특수 문자를 읽을 수 있는 HTML으로 안전하게 변환하는 도우미 함수가 있습니다.

2. 개인화 실행:
호출되면 Adobe의 웹 SDK에 요청(sendEvent)을 전송하여 페이지의 특정 영역(#ajo-offer 요소)에 대해 개인화된 콘텐츠를 가져옵니다.
오퍼가 반환되면 HTML을 디코딩하고 페이지에 삽입합니다.
아무것도 반환되지 않으면 경고가 기록됩니다.

3. SDK 대기:
Adobe의 SDK(alloy)는 비동기식으로 로드되므로 스크립트는 요청을 수행하기 전에 완전히 로드될 때까지 대기합니다.
오류를 방지하기 위해 200밀리초마다 최대 20번까지 합금을 확인합니다.

4. 페이지 로드 시: 페이지 로드가 완료되면 스크립트는 waitForAlloy()를 호출하여 프로세스를 시작합니다.



```javascript
< script >
    function decodeHtmlEntities(html) {
        const txt = document.createElement("textarea");
        txt.innerHTML = html;
        return txt.value;
    }


function runPersonalization() {
    console.log("🚀 Sending personalization request to AJO...");
    alloy("sendEvent", {
        renderDecisions: true,
        personalization: {
            surfaces: ["#ajo-offer"]
        }
    }).then(result => {
        console.log("🔍 Web SDK decision response:", result);

        const decision = result.propositions?.[0];
        const html = decision?.items?.[0]?.data?.content;

        const container = document.getElementById("ajo-offer");
        if (html && container) {
            const decodedHtml = decodeHtmlEntities(html);
            console.log("✅ Offer HTML content (decoded):", decodedHtml);
            container.innerHTML = decodedHtml;
        } else {
            console.warn("⚠️ No personalized offer returned.");
        }


    }).catch(error => {
        console.error("❌ sendEvent failed:", error);
    });
}

function waitForAlloy(callback, retries = 20) {
    if (typeof alloy === "function") {
        callback();
    } else if (retries > 0) {
        console.log("⌛ Waiting for Alloy...");
        setTimeout(() => waitForAlloy(callback, retries - 1), 200);
    } else {
        console.error("❌ alloy is not loaded after waiting.");
    }
}

// Trigger initial personalization on page load
document.addEventListener("DOMContentLoaded", function() {
    waitForAlloy(() => runPersonalization());
}); <
/script>
```

[샘플 HTML 페이지 및 관련 에셋은 여기에서 다운로드할 수 있습니다.](assets/web-page-assets.zip)
