---
title: 대상자 만들기
description: 사용자 투자 환경 설정(주식, 채권, CD)을 기반으로 AJO 대상 만들기
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---


# 사용자 투자 환경 설정(주식, 채권, CD)을 기반으로 AJO 대상 만들기

이 자습서에서는 웹 양식을 통해 사용자 환경 설정을 캡처하고, 해당 데이터를 Adobe Experience Platform(AEP)로 실시간으로 전송하고, 선택 항목에 따라 사용자를 타깃팅된 대상으로 동적으로 자격을 부여하는 방법을 알아봅니다. Adobe 태그(Launch), AEP Web SDK(Alloy.js) 및 Edge 세그멘테이션을 결합하면 주식, 채권 또는 양도성예금증서(CD)에 관심이 있는 고객에게 즉시 개인화할 수 있습니다.

## 이 자습서의 사전 요구 사항

* Adobe Experience Platform 액세스

* Adobe Experience Platform 개념(프로필, 대상, 데이터 세트)에 대한 기본 이해

* Adobe 태그(Launch)에 익숙함 - 데이터 요소 및 규칙 설정

* 기본 JavaScript 지식(간단한 기능 읽기 및 쓰기)

* 브라우저 개발 도구 사용 기능(콘솔 및 네트워크 탭)


## 목표

이 자습서의 목적은 Adobe Experience Platform(AEP)에서 세 개의 서로 다른 대상을 빌드하고 자격을 부여하는 것입니다.

* 주식에 관심이 있는 고객

* 채권에 관심이 있는 고객

* CD에 관심이 있는 고객

사용자는 웹 양식을 통해 환경 설정을 제출하고 Adobe Launch를 사용하여 AEP Web SDK을 통해 이러한 환경 설정을 수집하므로 실시간 대상 자격이 활성화됩니다.

## 사용된 도구

* Adobe Experience Platform(AEP)

* Adobe Experience Platform 태그

* AEP 웹 SDK(Alloy.js)

* AEP Edge 세그멘테이션

* 기본 설정 양식이 있는 웹 페이지





