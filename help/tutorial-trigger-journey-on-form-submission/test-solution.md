---
title: 솔루션 테스트
description: 양식 제출 시 이메일을 보낼 여정 만들기
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00Z
jira: KT-20014
source-git-commit: 6e773afb6bf1770467f9c02739e6b3ede29c81f4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# 솔루션 테스트


솔루션 테스트
>[!VIDEO](https://video.tv.adobe.com/v/3478546)

## 샘플 자산 배포

Node.js가 설치되어 있지 않으면 다운로드한 후 [여기에서 설치](https://nodejs.org/)하세요.

다음을 실행하여 설치 확인:

`node -v`

`npm -v`

## 프로젝트 폴더 설정

다음 명령을 사용하여 샘플 앱에 대한 새 디렉터리를 만듭니다.

`mkdir trigger-journey `

`cd trigger-journey`

## 프로젝트 초기화

`npm init -y`

## 필요한 프레임워크 설치

`npm install express dotenv axios cors`

## 에셋 파일 복사

* [project-root.zip](assets/project-root.zip)의 압축을 풀고 내용을 `trigger-journey` 폴더에 넣습니다.

* `public` 폴더에 `trigger-journey` 폴더를 만듭니다.
* 공용 폴더에 [index.zip]의 압축 풀기
* `.env` 파일을 적절한 값으로 업데이트합니다. 이러한 값은 HTTP Source 연결을 만드는 동안 다운로드한 cURL 명령에서 사용할 수 있습니다

## 서버 실행

`trigger-journey` 디렉터리에 있는지 확인하십시오.
`node server.js` 명령 실행
브라우저를 [웹 페이지](http://localhost:3000/)&#x200B;(으)로 지정
양식을 작성하여 제출하십시오. 여정이 트리거되고 양식에 입력한 이메일 ID로 이메일이 전송됩니다.


