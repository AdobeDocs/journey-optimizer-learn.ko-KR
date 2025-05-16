---
title: 솔루션 테스트
description: 솔루션 테스트
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
source-git-commit: 68bd0a65e7d7f2d57f9620e76555485a1a79b4ae
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---

# ID 결합 테스트

이 샘플 애플리케이션은 CRM ID가 Adobe Experience Platform(AEP)로 전송되기 전에 서버측에서 사용자 자격 증명의 유효성을 검사하는 실제 로그인 흐름을 시뮬레이션합니다. 로컬 Node.js 서버는 웹 페이지를 안전하게 제공하고, 기본 인증 논리를 처리하며, Adobe Launch 또는 Web SDK 기능을 방해할 수 있는 브라우저 제한(예: 차단된 로컬 파일 액세스 또는 CORS 헤더 누락)을 방지하는 데 사용됩니다. 이 설정을 사용하면 경험이 실제 프로덕션 환경에 더 가깝게 유지됩니다.

## node.js 설치

Node.js가 설치되어 있지 않으면 다운로드한 후 [여기에서 설치](https://nodejs.org/)하세요.

다음을 실행하여 설치 확인:

`node -v`

`npm -v`

## 프로젝트 폴더 설정

다음 명령을 사용하여 샘플 앱에 대한 새 디렉터리를 만듭니다

`mkdir aep-demo`

`cd aep-demo`

## 프로젝트 초기화

`npm init -y`

## Express 설치(웹 서버 프레임워크)

`npm install express`

## server.js 파일 만들기

```javascript
const express = require('express');
const path = require('path');
const app = express();
const PORT = 3000;

// Serve static files from the current directory
app.use(express.static(__dirname));

app.listen(PORT, () => {
  console.log(`Server is running at http://localhost:${PORT}`);
});
```

## HTML/Assets 추가

제공된 모든 [HTML 및 CSS 파일](assets/login-app-files.zip)을 이 폴더에 복사하십시오. index.html 파일의 `<head>` 섹션 내에 AEP 태그 스크립트를 복사하여 붙여 넣으십시오.

## 서버 실행

`node server.js`

## 테스트

`http://localhost:3000` URL을 엽니다. alice/pass123을 사용하는 로그인

## AEP Debugger 사용

Adobe Experience Platform Debugger은 웹 사이트에서 Adobe Experience Platform으로 전송되는 데이터의 유효성을 검사하는 데 도움이 되는 강력한 브라우저 확장 기능입니다. 이 메서드는 Adobe 웹 SDK(alloy.js)를 통해 identityMap이 올바르게 구성되고 전송되는지 확인하는 데 특히 유용합니다.

AEP Debugger를 사용하여 로그인 이벤트를 테스트하고, ID 결합을 확인하고(예: 전달되는 ECID 및 CRMID), AEP 태그 규칙 및 데이터 요소가 예상대로 실행되도록 합니다. 발신 이벤트, ID 정보 및 XDM 페이로드에 대한 실시간 가시성을 제공합니다. 이는 프로필 강화 및 대상 자격 조건 문제 해결에 중요합니다.

다음 스크린샷은 올바르게 전달되는 ID &quot;FIN001&quot;을 보여 줍니다.
![aep-debugger](assets/aep-debugger.png)

## AEP에서 ID 결합을 확인하는 단계

* AEP에 로그인
* 고객 -> 프로필 ->찾아보기 로 이동합니다.
* FinWise CRM ID = FIN001 검색
* 프로필을 열고 ID 섹션을 확인합니다. 나열된 CRMID와 ECID가 모두 표시됩니다.   이를 통해 두 ID가 단일 프로필로 결합되었음을 알 수 있습니다.



