---
title: 샘플 CRM 데이터를 AEP 프로필 데이터 세트로 가져오기
description: 'AEP이 ECID와 같은 공유 식별자를 기반으로 이러한 프로필을 익명 웹 방문자와 올바르게 연결할 수 있는지 확인하기 위해 샘플 레코드(예: CRMID, 이메일, 수입, 우편 번호 포함)를 가져옵니다.'
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
source-git-commit: 461906416a976ef9a9dea4fdb583b853b4fe61c7
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 4%

---

# 샘플 CRM 데이터를 AEP 프로필 데이터 세트로 가져오기

ID 결합을 시작하려면 샘플 CRM 프로필 데이터를 Adobe Experience Platform의 프로필 활성화 스키마에 연결된 데이터 세트로 가져옵니다

## 사용자 지정 네임스페이스 만들기

* 고객 -> ID -> ID 네임스페이스 만들기 로 이동합니다.
* 개별 교차 장치 ID 를 선택하고 아래 스크린샷에 표시된 대로 표시 이름과 ID 기호를 제공합니다.
  ![custom-namespace](assets/custom-namespace.png)

## 프로필 활성화 스키마 만들기

**_FinWiseProfileSchema_**이라는 개별 프로필 스키마를 만듭니다. annualIncome, email, firstName, lastName 및 loyaltyStatus와 같은 필드를 포함합니다.
SystemIdentifier 개체 아래에 ID 필드 **_crmid_**&#x200B;을(를) 추가합니다. crmid 필드를 ID 및 기본 필드로 표시


![프로필 스키마](assets/finwise-profile-schema.png)

## 샘플 데이터 준비

| crmId | 이름 | 성 | 이메일 | loyaltyStatus | 우편번호 | annualIncome |
|--------|-----------|----------|-------------------------|---------------|---------|--------------|
| FIN001 | 앨리스 | 웡 | alice.wong@example.com | 골드 | 92128 | 120000 |
| FIN002 | Bob | Smith | bob.smith@example.com | 실버 | 92126 | 85000 |
| FIN003 | 찰리 | 김 | charlie.kim@example.com | 플래티넘 | 60614 | 175000 |
| FIN004 | 다이아나 | Lee | diana.lee@example.com | 골드 | 30303 | 98000 |
| FIN005 | 이선 | 갈색 | ethan.brown@example.com | 브론즈 | 75201 | 60000 |

## CSV 파일 수집

* 이전 단계에서 만든 **_FinWiseProfileSchema_**&#x200B;을(를) 기반으로 **_FinWiseCustomerDataSetWithAnnualIncome_**&#x200B;이라는 데이터 세트를 만듭니다

* 연결 -> 소스 -> 로컬 시스템으로 이동합니다.
* 로컬 파일 업로드에서 **_데이터 추가_**&#x200B;를 선택합니다. 대상 데이터 집합으로 _**FinWiseCustomerDataSetWithAnnualIncome**_을(를) 선택하십시오.
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* 다음 화면으로 이동합니다. [csv 파일](assets/finwise_profiles.csv)을 업로드하고 매핑을 확인하십시오
  ![매핑](assets/mappings.png)

* 마침을 클릭하여 데이터 수집 프로세스를 시작합니다

## 프로필 확인

* 고객 ->프로필 로 이동하고 FIN001과 같은 FinWise CRM ID 또는 다른 유효한 값을 검색합니다
  ![프로필 확인](assets/verify-profiles.png)
