---
title: 교육 샌드박스 구성 - 소개
description: 교육을 위해 샌드박스를 구성하는 방법을 알아봅니다. 스키마를 구성하고, 샘플 데이터를 수집하고, 이벤트를 만드는 데 필요한 단계를 수행합니다.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 6%

---

# 교육 샌드박스 구성 - 소개 및 사전 요구 사항

![배너 튜토리얼 - 교육 샌드박스 구성](./assets/ajo-banner-configure-training-sandbox.png)

이 튜토리얼은 Adobe 제공 작업을 수행하는 관리자 및 데이터 엔지니어를 위해 설계되었습니다 [!DNL Journey Optimizer] 교육 환경. 스키마를 구성하고, 샘플 데이터를 수집하고, 이벤트를 만드는 데 필요한 단계를 알아봅니다. 또한 학습자가 작업을 확인할 수 있는 세 가지 테스트 프로필을 만듭니다.

제공된 샘플 데이터는 라는 가상의 스포츠 의류 회사를 기반으로 합니다 _[!DNL Luma]_. [!DNL Luma] 은 여러 국가의 상점, 웹 사이트를 통한 온라인 상의 존재감 및 모바일 앱을 보유하고 있습니다. [!DNL Luma] 은 Adobe Journey Optimizer을 사용하여 고객에게 연관성 있고 상황에 맞는 개인화된 경험을 제공합니다.

이 자습서가 끝나면 [!DNL Luma] 의 실습 연습에서 다루는 사용 사례 [Journey Optimizer 과제](/help/challenges/introduction-and-prerequisites.md) 섹션.

## 전제 조건

교육 샌드박스 설정을 시작하려면 먼저 다음을 수행해야 합니다.

1. 전용 개발 [샌드박스](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).

1. [이메일 메시지 사전 설정](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=en) 마케팅 및 트랜잭션 메시징용으로 구성되었습니다.

1. **[!UICONTROL 여정 관리자]** 및 **[!UICONTROL 데이터 관리자]** 교육 샌드박스에 대한 권한.

1. 사용자 [조직 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ko-KR).

1. Journey Optimizer 인스턴스에 구성된 샘플 데이터가 있는 JSON 파일:

   1. 다운로드 `luma-sample-data.zip` 파일 [여기](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip): 이 자습서에 필요한 모든 JSON 파일을 포함합니다.

   1. 다운로드 폴더에서 `luma-data.zip` 파일을 컴퓨터의 원하는 위치에 추가한 다음 압축을 풉니다.

      이러한 파일에는 교육 샌드박스에 대한 샘플 데이터가 있습니다.

   1. 각 파일을 열고 **`yourOrganizationID`** 및 을(를) (으)로 바꾸기 [조직 ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=ko-KR).

   1. 파일을 저장합니다.

## 그럼 시작해 보겠습니다

다음으로 시작 [수동 데이터 설정](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

이 단계에서는 필요한 데이터 구조를 정의합니다. 데이터 설정을 완료한 후 데이터를 샌드박스로 수집한 다음 이벤트를 설정할 수 있습니다.
