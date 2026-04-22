---
title: 로컬에서 응용 프로그램 실행
description: 로컬에서 샘플 애플리케이션을 설정하여 AJO을 사용한 웹 푸시 알림 흐름을 살펴봅니다.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# 로컬에서 응용 프로그램 실행

이 페이지에서는 Adobe Journey Optimizer을 사용하여 웹 푸시 알림 흐름을 테스트하고 탐색할 수 있도록 로컬에서 샘플 애플리케이션을 설정하는 과정을 안내합니다. 저장소를 복제하고 환경 변수를 구성한 다음 로컬 시스템에서 애플리케이션을 실행합니다.


다음 단계에 따라 로컬 시스템에서 샘플 응용 프로그램을 실행합니다.

## &#x200B;1. Node.js 설치

시스템에 **Node.js(버전 16 이상)**&#x200B;이(가) 설치되어 있는지 확인하십시오.

여기에서 [다운로드:](https://nodejs.org/)

설치 확인

```node -v```

```npm -v```


## &#x200B;2. 저장소 복제

```git clone https://github.com/gbedekar489/ajo-web-push.git```

```cd ajo-web-push```

## &#x200B;3. 종속성 설치

```npm install```

## &#x200B;4. 환경 변수 구성

루트 디렉토리에 .env 파일을 생성하고 다음을 추가합니다.

```
DATASTREAM_ID=your_datastream_id
ORG_ID=your_org_id
VAPID_PUBLIC_KEY=your_vapid_public_key
APP_ID=your_app_id
DATASET_ID=your_profile_dataset_id
PORT=3000
```

로컬에서 실행할 때 이러한 값은 .env 파일에서 읽혀집니다. 프로덕션(예: 렌더링)에서는 환경 변수로 구성됩니다.