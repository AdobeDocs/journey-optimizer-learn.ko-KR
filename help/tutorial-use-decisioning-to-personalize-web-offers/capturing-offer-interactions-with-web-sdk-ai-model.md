---
title: AI 모델 교육을 위한 Adobe Web SDK으로 오퍼 상호 작용 캡처
description: 이 문서는 Adobe Experience Platform Web SDK(alloy.js)를 사용하여 오퍼 노출 횟수 및 클릭 수와 같은 사용자 상호 작용 데이터를 캡처하는 데 중점을 둡니다. 이 데이터는 사용자 비헤이비어 및 컨텍스트 신호를 기반으로 오퍼의 등급을 지능적으로 매기기 위해 Adobe Journey Optimizer(AJO)에서 AI 모델을 교육할 수 있는 기반 역할을 합니다.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: dfb280df3453e7811dffd95b9af664b873a9af31
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---


# AI 모델 교육을 위한 Adobe Web SDK으로 오퍼 상호 작용 캡처

이 문서에서는 JavaScript 코드에서 직접 alloy(&quot;sendEvent&quot;, ...)를 호출하여 Adobe Experience Platform Web SDK을 사용하여 오퍼 상호 작용 이벤트(노출 횟수 또는 클릭 수 등)를 캡처하는 방법을 보여 줍니다. 이 데이터는 AEP에 수집되어 실시간 행동을 기반으로 보다 스마트한 오퍼 순위를 제공하기 위해 Adobe Journey Optimizer(AJO)의 AI 모델을 교육하는 데 사용됩니다.

## 전제 조건

시작하기 전에 다음 사항을 확인하십시오.

- Adobe Experience Platform Web SDK 확장이 설치된 작동 중인 Adobe Launch 속성입니다.

- AEP 샌드박스에 구성 및 매핑된 [데이터스트림](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)입니다.

- Launch가 배포되는 웹 사이트입니다.


## 오퍼 상호 작용 이벤트에 대한 스키마 및 데이터 세트 만들기

경험 이벤트를 수집하려면 먼저 이러한 이벤트를 전송할 데이터 세트를 만들어야 합니다.

이 [문서에 언급된 단계에 따라 필요한 스키마와 데이터 집합을 만드십시오](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)

## AEP에서 데이터 스트림 만들기

![데이터 스트림](assets/ai-model-data-stream.png)
데이터스트림에 Adobe Experience Platform 서비스 추가
![데이터 스트림 서비스](assets/data-stream-service.png)

## 웹 SDK으로 Adobe Experience Platform 태그 구성

확장 설정에서 다음을 수행합니다.

생성된 데이터 스트림을 사용하도록 Adobe Experience Platform Web SDK 확장 구성
