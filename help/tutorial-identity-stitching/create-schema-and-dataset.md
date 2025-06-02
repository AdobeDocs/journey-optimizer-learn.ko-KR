---
title: AEP에서 XDM 스키마, 데이터 세트 및 데이터 스트림 설정
description: XDM 스키마, 데이터 세트 및 데이터 스트림 만들기
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-18089
source-git-commit: 860f4fa4f6b491f3327776ba372bd5fa20e5d5d3
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# AEP에서 XDM 스키마, 데이터 세트 및 데이터 스트림 설정

## XDM 스키마 만들기

웹 페이지에서 Adobe Experience Platform 웹 SDK(Alloy.js)를 사용하려면 AEP 태그를 XDM 이벤트 스키마에 매핑된 데이터 스트림에 연결해야 합니다. 웹 SDK(alloy.sendEvent)는 XDM ExperienceEvent 클래스를 기반으로 하는 XDM 스키마를 준수해야 하는 데이터를 경험 이벤트로 AEP에 보냅니다.

XDM 스키마를 만들려면

* Adobe Experience Platform에 로그인
* 데이터 관리 -> 스키마 -> 스키마 만들기

* **_재무 관리자_**&#x200B;라는 XDM 이벤트 기반 스키마를 만듭니다. 스키마 만들기에 익숙하지 않은 경우 이 [설명서](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)를 따르십시오.


* 프로필에 대해 스키마가 활성화되어 있는지 확인합니다.

## 스키마를 기반으로 데이터 세트 만들기

Adobe Experience Platform(AEP)의 **데이터 집합**&#x200B;은(는) 정의된 XDM 스키마를 기반으로 데이터를 수집, 저장 및 활성화하는 데 사용되는 구조화된 저장소 컨테이너입니다.


* 데이터 관리 -> 데이터 세트 -> 데이터 세트 만들기
* 이전 단계에서 만든 XDM 스키마(재무 관리자)를 기반으로 **_재무 관리자 데이터 집합_**&#x200B;이라는 데이터 집합을 만듭니다.

* 프로필에 대해 데이터 세트가 활성화되어 있는지 확인합니다.

## 데이터 스트림 만들기

Adobe Experience Platform의 데이터 스트림은 웹 사이트 또는 앱을 Adobe 서비스에 연결하는 보안 파이프라인(또는 고속도로)과 유사하므로 데이터가 이동하고 개인화된 콘텐츠가 다시 흐를 수 있습니다.

* 데이터 수집 > 데이터스트림으로 이동한 다음 새 데이터스트림을 클릭합니다. 데이터 스트림 이름을 **_재무 관리자 데이터 스트림_**&#x200B;으로 지정합니다.

* 아래 스크린샷과 같이 다음 세부 정보를 제공합니다
  ![데이터스트림](assets/datastream.png)
* 저장 을 클릭한 다음 매핑 추가 를 클릭하고 아래와 같이 Adobe Experience Platform 서비스 및 이벤트 데이터 세트를 추가합니다
  ![데이터스트림 매핑](assets/datastream-service.png)

* 적절한 이벤트 데이터 세트(이전에 만든 데이터 세트)를 선택합니다.

* 데이터스트림을 저장합니다.

