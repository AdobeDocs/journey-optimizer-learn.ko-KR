---
title: 교육 샌드박스 구성 - 소개
description: 교육 목적으로 샌드박스를 구성하는 방법을 알아봅니다. 스키마를 구성하고 샘플 데이터를 수집하며 이벤트를 만드는 데 필요한 단계를 따르십시오.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
source-git-commit: 79249cf6ecd08c38c075a4e27fa9cf74073491af
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 6%

---


# 교육 샌드박스 구성 - 소개 및 사전 요구 사항

![배너 자습서 - 교육 샌드박스 구성](./assets/ajo-banner-configure-training-sandbox.png)

이 자습서는 Adobe Journey Optimizer 교육 환경을 제공하는 관리자 및 데이터 엔지니어를 위해 설계되었습니다. 스키마를 구성하고 샘플 데이터를 수집하며 이벤트를 만드는 데 필요한 단계를 알아봅니다. 또한 학습자가 자신의 작업을 확인할 수 있도록 하는 3개의 테스트 프로필을 만듭니다.

제공된 샘플 데이터는 _[!DNL Luma]_. [!DNL Luma] 는 여러 국가에 스토어, 웹 사이트를 통한 온라인 유무, 모바일 앱을 보유하고 있습니다. [!DNL Luma] 은 Adobe Journey Optimizer을 사용하여 고객에게 연결되고 상황에 맞는 개인화된 경험을 제공합니다.

이 자습서를 마치면 다음을 지원하는 샌드박스가 있습니다 [!DNL Luma] 의 실습 연습에서 다루는 사용 사례 [Journey Optimizer 과제](/help/challenges/introduction-and-prerequisites.md) 섹션을 참조하십시오.

## 전제 조건

교육 샌드박스 설정을 시작하려면 먼저 다음을 확인하십시오.

1. 전용 개발 [샌드박스](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).
1. [이메일 메시지 사전 설정](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/channel-configuration/set-up-email-channel.html?lang=en) 마케팅 및 트랜잭션 메시징용으로 구성되었습니다.
1. **[!UICONTROL 여정 관리자]** 및 **[!UICONTROL 데이터 관리자]** 교육 샌드박스의 권한.
1. 사용자 [조직 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ko-KR).

1. Journey Optimizer 인스턴스에 구성된 샘플 데이터가 있는 JSON 파일:

   1. 다운로드 `luma-data.zip` 파일 [여기](/help/tutorial-configure-a-training-sandbox/assets/luma-data.zip): 이 자습서에 필요한 모든 JSON 파일을 포함합니다.

   1. 다운로드 폴더에서 `luma-data.zip` 파일을 컴퓨터의 원하는 위치에 저장하고 압축을 해제합니다.

      다음 세 개의 JSON 파일이 있어야 합니다. `luma-crm.json`, `luma-loyalty.json`, `luma-products.json`.

      이러한 파일은 샌드박스에 수집하는 샘플 데이터를 포함합니다.

   1. 각 파일을 열고 **`yourOrganizationID`** 그리고 그것을 [조직 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en).

   1. 파일을 저장합니다.

## 그럼 시작해 보겠습니다

다음으로 시작 [수동 데이터 설정](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md). 이 단계에서는 필요한 데이터 구조를 정의합니다. 데이터 설정을 완료하면 데이터를 샌드박스에 수집한 다음 이벤트를 설정할 수 있습니다.
