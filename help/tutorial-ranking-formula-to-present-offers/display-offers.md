---
title: 솔루션을 테스트할 웹 페이지 만들기
description: Decisioning을 사용하여 전달된 개인화된 오퍼를 테스트하는 웹 페이지입니다.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00Z
jira: KT-18188
recommendations: noDisplay, noCatalog
exl-id: 6b1eec78-153c-4ea5-acfe-2dcc6f1e6078
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# 솔루션을 테스트할 웹 페이지 만들기

이 샘플 애플리케이션은 CRM ID가 Adobe Experience Platform(AEP)로 전송되기 전에 서버측에서 사용자 자격 증명의 유효성을 검사하는 실제 로그인 흐름을 시뮬레이션합니다. 로컬 Node.js 서버는 웹 페이지를 안전하게 제공하고, 기본 인증 논리를 처리하며, Adobe Launch 또는 Web SDK 기능을 방해할 수 있는 브라우저 제한(예: 차단된 로컬 파일 액세스 또는 CORS 헤더 누락)을 방지하는 데 사용됩니다. 이 설정을 사용하면 경험이 실제 프로덕션 환경에 더 가깝게 유지됩니다.

개인화된 오퍼는 사용자가 로그인한 후에만 표시되며, 이 시점에서 사용자의 CRM ID와 ECID(Experience Cloud ID) 간 ID 결합이 완료됩니다. 이 ID 결합을 통해 Adobe Journey Optimizer(AJO)가 프로필을 정확하게 인식하고 타겟팅된 오퍼를 반환할 수 있습니다.

로그인에 성공하면 사용자에 대해 사용 가능한 오퍼를 검색하기 위해 개인화 요청이 AJO으로 전송됩니다. 이러한 오퍼는 HTML 조각으로 반환되며, 각각 오퍼 이름과 우편 번호 및 소득 수준과 같은 세분화 세부 정보를 포함하는 데이터 태그 속성(예: data-tags=&quot;ajo offer-vacation-based-cd zip-92128 income-high&quot;)이 포함됩니다.

그런 다음 JavaScript은 이러한 HTML 블록을 구문 분석하고 각 블록을 회전식 항목 컨테이너 내에 래핑합니다. 항목이 회전식 트랙 내에 가로로 배열되어 있어 회전 가능한 탐색이 가능합니다. 이전 및 다음 단추(◀ 및 ▶)를 사용하면 개인화된 오퍼를 한 번에 하나씩 전환할 수 있습니다.

이 설정은 응답성과 맞춤 환경을 제공하여 플랫폼 간에 신원이 안전하게 결합된 후에만 각 사용자가 재무 프로필과 관련된 오퍼를 볼 수 있도록 합니다.

## 이 솔루션 테스트

* 기존 Node.js 프로젝트 내에 ranking-formula라는 폴더를 만듭니다.

* [제공된 파일을 이 순위 수식 폴더로 압축 해제합니다.](assets/ranking-formula.zip)

* 폴더로 이동하고 서버를 시작하여 앱을 실행합니다.
   * `cd ranking-formula`

   * `node server.js`


* 브라우저를 열고 http://localhost:3000/formula.html으로 이동합니다.

* alice/pass123을 사용하여 로그인

Alice는 92128 우편번호에 있으므로 해당 위치에 맞는 오퍼가 표시됩니다.
