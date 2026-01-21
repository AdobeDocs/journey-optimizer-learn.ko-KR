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
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---

# 솔루션 테스트

## 샘플 자산 배포

Node.js가 설치되어 있지 않으면 다운로드한 후 [여기에서 설치](https://nodejs.org/)하세요.

다음을 실행하여 설치 확인:

`node -v`

`npm -v`

## 프로젝트 폴더 설정

다음 명령을 사용하여 샘플 앱에 대한 새 디렉터리를 만듭니다.

`mkdir frequency-capping `

`cd frequency-capping `

## 프로젝트 초기화

`npm init -y`

## 필요한 프레임워크 설치

`npm install express`

## 에셋 파일 복사

* 압축을 풀고 [server.zip](assets/server.zip)의 내용을 `frequency-capping` 폴더에 넣습니다.
* [public.zip](assets/public.zip)의 콘텐츠를 &#39;빈도 제한&#39; 폴더로 추출하십시오.

## Javascript 파일에서 표면 URL 업데이트

`frequency-capping.js`에 있는 `public\scripts`을(를) 열고 캠페인에 사용된 채널 구성과 일치하도록 표면 속성을 업데이트합니다.

## 노드 js 서버 시작

`c:\frequency-capping` 폴더로 이동합니다. `node server.js` 명령을 실행하여 포트 3000에서 노드 js 서버를 시작합니다.


## Adobe Experience Platform 태그 속성 업데이트

텍스트 편집기의 `frequency-capping.html` 폴더에 있는 `public` 파일을 열고 스크립트 태그를 이 자습서의 이전 단계에서 만든 Adobe Experience Platform 태그 속성의 스크립트 태그로 바꿉니다. 파일을 저장해야 합니다.

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## 오퍼와 상호 작용

* 즐겨찾는 브라우저에서 [웹 페이지](http://localhost:3000)을(를) 엽니다.
* 오퍼와 상호 작용
* 페이지 새로 고침
* 빈도 제한 규칙에 따라 새 오퍼가 표시됩니다

## 보고서 보기

* Journey Optimizer에 로그인
* 여정 관리 ->캠페인으로 이동합니다.
* 캠페인을 클릭한 다음 보고서 메뉴에서 적절한 보고서를 선택합니다.
