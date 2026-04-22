---
title: 데이터 스트림 만들기
description: 이 페이지에서는 웹 SDK에서 데이터를 수집하고 Adobe Experience Platform 및 Adobe Journey Optimizer으로 라우팅하는 데 필요한 AEP에서의 데이터 스트림 생성을 안내합니다. 데이터 스트림은 웹 애플리케이션과 Adobe 서비스 간의 연결 역할을 하므로 푸시 구독과 이벤트 데이터를 처리할 수 있습니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# 데이터 스트림 만들기

Adobe Experience Platform(AEP)의 데이터 스트림은 웹 SDK에서 전송된 데이터를 수신하는 엔드포인트 역할을 합니다. 이 데이터는 구성된 서비스(예: AEP, Adobe Analytics 또는 Adobe Journey Optimizer)로 라우팅됩니다. 이 자습서에서는 활성화를 위해 웹 푸시 구독 데이터 및 price.drop 이벤트를 AEP에 전송하는 데 데이터스트림을 사용합니다.

## 푸시 알림 추적을 위한 이벤트 스키마 만들기

이름이 `SchemaForPushNotification`인 새 XDM ExperienceEvent 스키마를 만듭니다. `Push Notification Tracking` 및 `Commerce Details` 필드 그룹을 이 스키마에 추가합니다. Commerce 세부 정보 필드 그룹의 필드는 제품 정보를 캡처하고 사용자 지정 price.drop 이벤트를 트리거하는 데 사용됩니다.

![이벤트 스키마](assets/event-schema.png)

## 사용자의 동의를 저장할 프로필 스키마 만들기

이 자습서에서는 기본 `AJO Push Profile Schema`을(를) 사용합니다. 이 스키마는 웹 푸시 알림을 전달하는 데 필요한 푸시 토큰을 포함하여 사용자의 푸시 구독 세부 정보를 저장합니다.

![profile_schema](assets/profile-schema.png)

## 스키마에 대한 데이터 세트 만들기

이전에 만든 이벤트 스키마를 사용하여 `DataSetForPushNotification`(이)라는 데이터 집합을 만듭니다. 프로필 데이터의 경우 푸시 프로필 스키마와 연결된 기본 `AJO Push Profile Dataset`을(를) 사용합니다. .env 파일을 통해 응용 프로그램을 구성할 때 자습서에서 나중에 필요하므로 `DataSetForPushNotification` ID를 메모하십시오.

## 이벤트 및 프로필 데이터 세트를 사용하여 데이터 스트림 만들기

이전 단계에서 만든 이벤트 및 프로필 데이터 세트를 사용하여 WebPushDataStream이라는 새 데이터 스트림을 만듭니다. .env 파일을 통해 애플리케이션을 구성할 때 자습서의 후반부에 필요하므로 데이터 스트림 ID를 메모하십시오.

![데이터스트림](assets/datastream.png)
