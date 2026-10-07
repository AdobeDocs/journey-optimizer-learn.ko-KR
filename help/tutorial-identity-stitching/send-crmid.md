---
title: 로그인 활동을 모방할 샘플 애플리케이션 구축
description: 로그인 흐름을 시뮬레이션하는 샘플 Node.js 애플리케이션을 빌드합니다.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: e080149c-0ac0-4559-b99d-ebad9f03b98b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%
---
# 로그인 활동을 모방할 샘플 애플리케이션 구축

Node.js 서버에 구축되고 배포된 이 샘플 애플리케이션은 사용자가 로그인할 때 CRM ID를 Adobe Experience Platform(AEP)로 보내는 방법을 보여 줍니다. 애플리케이션은 서버 측에서 사용자 자격 증명의 유효성을 검사하는 로그인 플로우를 시뮬레이션합니다. 로그인에 성공하면 사용자의 CRM ID가 검색되어 adobeDataLayer로 푸시되고 Adobe Experience Platform Tags(이전의 Adobe Launch)에서 해당 규칙이 트리거됩니다.

attachLoginHandler 함수는 제출 이벤트 리스너를 로그인 양식에 연결합니다. 양식 제출 시 기본 작업을 방지하고, 사전 정의된 사용자 객체에 대해 자격 증명을 확인하고, 유효한 경우 CRM ID를 검색합니다. 이 함수는 CRM ID와 인증 상태를 사용하는 userloggedin 이벤트를 adobeDataLayer로 푸시하고 Adobe Experience Platform Tags가 이 이벤트를 선택하여 데이터를 Adobe Experience Platform(AEP)로 보냅니다.


```javascript
function attachLoginHandler() {
    const form = document.getElementById("loginForm");
    if (!form) return;

    form.addEventListener("submit", function(e) {
        e.preventDefault();
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;

        if (users[username] && users[username].password === password) {
            const crmid = users[username].crmid;
            window.adobeDataLayer = window.adobeDataLayer || [];
            debugger;
            window.adobeDataLayer.push({
                event: "UserLoggedIn",
                user: {
                    crmid: crmid,
                    authenticatedState: "authenticated"
                }
            });
        }
    });
}
```

Adobe Experience Platform 태그 스크립트는 일반적으로 다음과 같은 `<script>` 태그를 사용하여 HTML 페이지의 `<head>` 섹션에 포함되어 있습니다.

`<script src="https://assets.adobedtm.com/b5eu4857867/4e4d84957/launch-b69e276bb9b5-development.min.js" async crossorigin="anonymous"></script>`

AEP 태그 스크립트는 이전 단계에서 만든 웹 SDK 지원 속성을 게시하고 환경 탭에서 포함 코드를 복사하여 가져온 것입니다.
