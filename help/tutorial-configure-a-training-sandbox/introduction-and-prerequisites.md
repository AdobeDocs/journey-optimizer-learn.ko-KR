---
title: 교육 샌드박스 구성 - 소개
description: 교육용 샌드박스를 구성하는 방법을 알아봅니다. 스키마를 구성하고 샘플 데이터를 수집하고 이벤트를 만드는 데 필요한 단계를 수행합니다.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 81f5cc22d46f89ee1c7164a92988311ca6036b8b
workflow-type: ht
source-wordcount: '338'
ht-degree: 100%

---

# 교육 샌드박스 구성 - 소개 및 사전 요구 사항

![배너 튜토리얼 - 교육 샌드박스 구성](./assets/ajo-banner-configure-training-sandbox.png)

이 튜토리얼은 Adobe [!DNL Journey Optimizer] 교육 환경을 제공하는 업무를 맡은 관리자와 데이터 엔지니어를 위해 마련되었습니다. 스키마를 구성하고 샘플 데이터를 수집하고 이벤트를 만드는 데 필요한 단계를 알아봅니다. 또한 학습자가 자신의 작업 결과물을 확인할 수 있도록 세 가지 테스트 프로필을 만듭니다.

여기에서 제공하는 샘플 데이터는 _[!DNL Luma]_라는 가상의 스포츠 의류 회사를 기반으로 합니다. [!DNL Luma]는 여러 국가에 매장이 있으며 웹 사이트를 통해 온라인에서 존재감을 갖춘 한편 모바일 앱을 운영하고 있습니다. [!DNL Luma]는 Adobe Journey Optimizer를 사용하여 고객에게 연결되고 상황에 맞는 개인화된 경험을 제공합니다.

이 튜토리얼을 마칠 때 사용자는 [Journey Optimizer 과제](/help/challenges/introduction-and-prerequisites.md) 섹션의 실습에서 다루는 [!DNL Luma] 사용 사례를 지원할 샌드박스를 가지게 됩니다.

## 사전 요구 사항

교육 샌드박스 설정을 시작하려면 먼저 다음 사항을 준비해야 합니다.

1. 전용 개발 [샌드박스](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=ko).

1. 마케팅 및 트랜잭션 메시지용으로 구성한 [이메일 메시지 사전 설정](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=ko).

1. 교육 샌드박스에 대한 **[!UICONTROL 여정 관리자]** 및 **[!UICONTROL 데이터 관리자]** 권한.

1. 자신의 [조직 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ko).

1. 샘플 데이터가 있는 JSON 파일(Journey Optimizer 인스턴스에 구성):

   1. 이 튜토리얼에 필요한 JSON 파일 전체가 들어 있는 `luma-sample-data.zip` 파일을 [여기](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip)에서 다운로드할 수 있습니다.

   1. 다운로드 폴더의 `luma-data.zip` 파일을 컴퓨터에서 원하는 위치로 옮긴 다음 압축을 풉니다.

      이 파일에는 교육 샌드박스에서 사용할 샘플 데이터가 있습니다.

   1. 각 파일을 열고 **`yourOrganizationID`** 부분을 찾아 자신의 [조직 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ko)로 바꿉니다.

   1. 파일을 저장합니다.

## 그럼 시작해 보겠습니다

먼저 [수동 데이터 설정](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md)부터 시작합니다.

이 단계에서는 필요한 데이터 구조를 정의합니다. 데이터 설정을 완료한 다음에는 데이터를 샌드박스로 수집하고 이벤트를 설정할 수 있습니다.
