---
title: 수동으로 데이터 구조 설정
description: 필요한 ID 네임스페이스를 만들고 Luma 샘플 데이터 구조를 정의합니다.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 10%

---

# 수동으로 데이터 설정

이 섹션에서는 필요한 ID 네임스페이스를 만들고 [!DNL Luma] 다음을 만들어 샘플 데이터 구조 [[!UICONTROL 스키마]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ko-KR-KR).

>[!TIP]
>비디오 튜토리얼 보기 [ID 매핑](/help/set-up-data/map-identities.md) 시작하기 전에.

## 1단계: ID 네임스페이스 만들기

이 단계에서는 다음을 위한 ID 네임스페이스를 만듭니다. [!DNL Luma] 사용자 정의 id 필드 이름 `lumaLoyaltyId`, `lumaCrmId`, 및 `lumaProductSKU`. 동일한 네임스페이스에서 일치하는 두 개의 값을 사용하면 두 개의 데이터 소스에서 ID 그래프를 구성할 수 있으므로 ID 네임스페이스는 실시간 고객 프로필을 빌드하는 데 중요한 역할을 합니다.

다음을 만들어 시작: [!UICONTROL 네임스페이스] 대상: [!DNL Luma Loyalty ID] 스키마:

1. Journey Optimizer 사용자 인터페이스에서 **[!UICONTROL 고객]** > **[!UICONTROL ID]** 왼쪽 탐색.

1. 선택 **[!UICONTROL ID 네임스페이스 만들기]**.

1. 다음 세부 정보를 제공합니다.

   | 표시 이름 | ID 기호 | 유형 |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL 교차 장치 ID] |

1. **[!UICONTROL 만들기]**&#x200B;를 선택합니다.

   ![네임스페이스 만들기](assets/createNamespace.png)

1. 동일한 단계에 따라 두 개의 네임스페이스를 더 만듭니다.

   | 표시 이름 | ID 기호 | 유형 |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL 교차 장치 ID] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL 비사용자 식별자] |

## 2단계: 스키마 만들기

이 단계에서는 6을 만들어 샘플 데이터의 구조를 정의합니다 [[!UICONTROL 스키마]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ko-KR-KR):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product Catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events] 스키마](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Offline Purchase Events Schema]](#create-additional-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-additional-schemas)

>[!TIP]
>
>비디오 튜토리얼을 시청하십시오. [스키마 만들기](/help/set-up-data/create-schema.md) 시작하기 전에.

### 만들기 [!DNL Luma Loyalty Schema] {#create-luma-loyalty-schema}

이 섹션에서는 다음을 만드는 방법을 설명합니다. [!DNL Luma Loyalty] 필드 그룹을 스키마하고 구성합니다.

#### 스키마 만들기

1. 다음으로 이동 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 스키마]** 왼쪽 탐색.

1. 선택 **[!UICONTROL 스키마 만들기]** 오른쪽 위에 있습니다.

1. 드롭다운 메뉴에서 을(를) 선택합니다 **[!UICONTROL XDM 개별 프로필]**.

   개별 고객의 속성(점수, 상태 등)을 모델링하기 때문에 이 옵션을 선택합니다.

#### 기존 필드 그룹 추가

그런 다음 그룹을 사용하여 스키마에 필드 그룹을 추가하라는 메시지가 표시됩니다. 기존 필드 그룹을 추가하고 필드 그룹을 만들어야 합니다.

1. 다음에서 [!UICONTROL 스키마] 페이지, 필드 그룹 모달이 자동으로 열리지 않으면 **[!UICONTROL 추가]**.

   ![필드 그룹 추가](assets/add_field_group.png)

1. 다음에서 **[!UICONTROL 필드 그룹 추가]** 페이지에서 다음 필드 그룹을 활성화합니다.

   * **[!UICONTROL 인구 통계 세부 정보]** 이름 및 생년월일과 같은 기본 고객 데이터.

   * **[!UICONTROL 개인 연락처 세부 정보]** 이메일 주소 및 전화번호 등 기본 연락처 세부 정보.

   * **[!UICONTROL 고객 충성도 세부 정보]** 포인트, 가입된 날짜 또는 상태 등 고객 충성도 세부 정보. 충성도 필드 그룹은 목록의 맨 아래에 있으므로 검색하는 것이 가장 쉽습니다.

1. 선택 **[!UICONTROL 필드 그룹 추가]** 세 개의 필드 그룹을 모두 스키마에 추가합니다.

   ![표준 필드 그룹 선택](assets/addstandardFieldGroups.png)

1. 스키마의 최상위 노드를 선택합니다.

1. 입력 `Luma Loyalty Schema` (으)로 **[!UICONTROL 표시 이름]**.

#### 만들기 [!UICONTROL 필드 그룹] {#create-field-group}

Adobe은 스키마 간에 일관성을 유지하기 위해 모든 시스템 식별자를 단일 그룹으로 관리할 것을 권장합니다.

1. 다음에서 **[!UICONTROL 컴포지션]** 아래 섹션 [!UICONTROL 필드 그룹], 선택 **[!UICONTROL 추가]**.

1. 선택 **[!UICONTROL 새 필드 그룹 만들기]**.

1. 추가 `Luma Identity Profile Field Group` (으)로 **[!UICONTROL 표시 이름]**.

1. 추가 `system identifiers for XDM Individual Profile class` (으)로 **[!UICONTROL 설명]**.

1. **[!UICONTROL 필드 그룹 추가]**&#x200B;를 선택합니다.

   ![새 필드 그룹 만들기](assets/addnewfieldgroup.png)

#### 새 필드에 필드 추가 [!UICONTROL 필드 그룹]

비어 있는 새 필드 그룹이 스키마에 추가됩니다. + 단추를 사용하여 계층의 모든 위치에 새 필드를 추가할 수 있습니다. 이 경우 루트 수준에서 필드를 추가해야 합니다.

1. 선택 **[!UICONTROL +]** 스키마 이름 옆에 있습니다.

   이 단계에서는 아래에 필드를 추가합니다. **임차인 id** 네임스페이스를 사용하십시오.

1. 다음에서 **[!UICONTROL 필드 속성]** 사이드바에서 새 필드의 세부 사항을 추가합니다.

   * **필드 이름:** `systemIdentifier`

   * **[!UICONTROL 표시 이름]:** `System Identifier`

   * **유형:** 오브젝트

   * **[!UICONTROL 필드 그룹 할당]:** [!DNL Luma identifiers]

1. **[!UICONTROL 적용]**&#x200B;을 선택합니다.

   ![시스템 식별자 추가](assets/addsysteidentifier.png)

   아래에 두 필드 추가 `systemIdentifier` 개체:

   | [!UICONTROL 필드 이름] | [!UICONTROL 표시 이름] | [!UICONTROL 유형] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty Id` | [!UICONTROL 문자열] |
   | `crmId` | `CRM Id` | [!UICONTROL 문자열] |

![필드](./assets/add_fields.png)

#### ID 설정

이제 다음을 보유합니다. [!UICONTROL 네임스페이스] 및 [!DNL Luma Loyalty schema] 구성되었습니다. 데이터를 수집하려면 먼저 ID 필드에 레이블을 지정해야 합니다. 에 사용되는 각 스키마 [!UICONTROL 실시간 고객 프로필] 에는 기본 id가 지정되어야 하며, 수집되는 각 레코드에는 해당 필드의 값이 있어야 합니다.

1. 설정 **기본 ID**:

   다음에서 **[!DNL Luma Loyalty Schema]**:

   1. **[!DNL Luma Identity Profile Field Group]**&#x200B;을(를) 선택합니다.

   2. 다음 항목 선택 **[!DNL loyaltyId]** 필드.

   3. 다음에서 **[!UICONTROL 필드 속성]**, 활성화 **[!UICONTROL 신원]** 상자.

   4. 활성화 **[!UICONTROL 기본 ID]** 상자.

   5. 다음 항목 선택 `Luma Loyalty Id` 네임스페이스 **[!UICONTROL ID 네임스페이스]** 드롭다운 메뉴.

   6. **[!UICONTROL 적용]**&#x200B;을 선택합니다.

      ![기본 ID](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. 설정 **보조 id**:

   다음에서 **[!DNL Luma Loyalty Schema]**:

   1. **[!DNL Luma Identity Profile Field Group]**&#x200B;을(를) 선택합니다.

   2. 다음 항목 선택 `crmId` 필드.

   3. 다음에서 **[!UICONTROL 필드 속성]**, 활성화 **[!UICONTROL 신원]** 상자.

   4. 다음 항목 선택 `Luma CRM Id` 네임스페이스 **[!UICONTROL ID 네임스페이스]** 드롭다운입니다.

   5. **[!UICONTROL 적용]**&#x200B;을 선택합니다.

#### 프로필에 대해 활성화 및 스키마 저장

1. 스키마의 최상위 노드를 선택합니다.

1. 다음에서 [!UICONTROL 필드 속성], 활성화 **[!UICONTROL 프로필]**.

   스키마는 다음과 같아야 합니다.

   ![Luma 충성도 스키마](assets/lumaloyaltyschema.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

### 만들기 [!DNL Luma Product Catalog Schema] {#create-luma-product-catalog-schema}

1. 다음으로 이동 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 스키마]** 왼쪽 탐색.

1. 선택 **[!UICONTROL 스키마 만들기]** (오른쪽 상단).

1. 클래스를 만들려면 **[!UICONTROL 모든 스키마 유형 찾아보기]** 드롭다운 메뉴에서 을(를) 선택합니다.

1. 선택 **[!UICONTROL 새 클래스 만들기]**.

1. 표시 이름 추가: `Luma Product Catalog Class`.

1. 클래스를 할당합니다.

1. 만들기 [!UICONTROL 필드 그룹]:

   * 표시 이름: `Luma Product Catalog Field Group`

1. 에 다음 필드를 추가합니다. **[!DNL Luma Product Catalog Field Group]**.

   * 필드 이름: `product`

   * 표시 이름: `Product`

   * 유형: [!UICONTROL 오브젝트]

   * 필드 그룹: [!DNL Luma Product Catalog Field Group]

1. **[!UICONTROL 적용]**&#x200B;을 선택합니다.

1. 에 다음 필드를 추가합니다. **[!DNL Product]** 개체:

   | [!UICONTROL 필드 이름] | [!UICONTROL 표시 이름] | [!UICONTROL 유형] |
   |-------------|-----------|----------|
   | `sku` | `Product SKU` | [!UICONTROL 문자열] |
   | `name` | `Product Name` | [!UICONTROL 문자열] |
   | `category` | `Product Category` | [!UICONTROL 문자열] |
   | `color` | `Product Color` | [!UICONTROL 문자열] |
   | `size` | `Product Size` | [!UICONTROL 문자열] |
   | `price` | `Product Price` | [!UICONTROL 이중] |
   | `description` | `Product Description` | [!UICONTROL 문자열] |
   | `imageURL` | `Product Image URL` | [!UICONTROL 문자열] |
   | `stockQuantity` | `Product Stock Quantity` | [!UICONTROL 문자열] |
   | `url` | `Product URL` | [!UICONTROL 문자열] |

1. 설정 **[!DNL SKU]** 기본 ID로.
1. 추가 **[!UICONTROL 표시 이름]** `Luma Product Catalog Field Group` (으)로 [!UICONTROL 필드 그룹].

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

### 만들기 [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}

1. 다음으로 이동 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 스키마]** 왼쪽 탐색.

1. 다음 항목 선택 **[!UICONTROL 스키마 만들기]** 오른쪽 상단의 버튼.

1. 드롭다운 메뉴에서 을(를) 선택합니다 **[!UICONTROL 모든 스키마 유형 찾아보기]**.

1. 선택 **[!UICONTROL 새 클래스 만들기]**.

1. 표시 이름 추가: `Luma Business Event Class`.

1. 유형 선택: *[!UICONTROL 시계열]*.

1. 클래스를 할당합니다.

1. 만들기 [!UICONTROL 필드 그룹]:

   * 표시 이름: `Luma Product Inventory Event Details Field Group`

1. 추가 **[!UICONTROL 표시 이름]** `Luma Product Inventory Event Schema` 스키마에 매핑됩니다.

1. 에 다음 필드를 추가합니다. **[!DNL Luma Product Inventory Event Details Field Group]**:

   * 필드 이름: `inventoryEvent`

   * 표시 이름: `Inventory Event`

   * 유형: [!UICONTROL 오브젝트]

   * 필드 그룹: `Luma Product Inventory Event Details Field Group`

1. 에 다음 필드를 추가합니다. `Product Inventory Event Details` 개체:

   | [!UICONTROL 필드 이름] | [!UICONTROL 표시 이름] | [!UICONTROL 유형] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL 문자열] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL 문자열] |

   1. 을(를) 설정하려면 `stockEventType` 열거하려면 유형을 선택합니다. `string`.

   2. 아래쪽으로 스크롤하여 **[!UICONTROL 필드 속성]**.

   3. 사용 **[!UICONTROL 열거형]**.

   4. 입력 **[!UICONTROL 값] ([!UICONTROL label)]**: `restock` (`Restock`).

   5. 선택 **[!UICONTROL 행 추가]**.

   6. 입력 **[!UICONTROL 값] ([!UICONTROL label)]**: `outOfStock` (`Out of Stock`).

   7. **[!UICONTROL 적용]**&#x200B;을 선택합니다.

      ![enum](assets/enum.png)

1. 설정 `inventory.Event.sku` 다음으로 필드 **[!UICONTROL 기본 ID]** 사용 **[!DNL LumaProductSKU namespace]**.

1. 다음 항목 선택 `sku` 필드 및 관계에 대한 정의 `product.sku` 의 필드 **[!DNL Luma Product catalog Schema]** 스키마:

   1. 아래쪽으로 스크롤하여 **[!UICONTROL 필드 속성]**.

   2. 사용 **[!UICONTROL 관계]**.

      1. **[!UICONTROL 참조 스키마]**: [!DNL Luma Product Catalog Schema].

      2. **[!UICONTROL 참조 ID 네임스페이스]**: [!DNL LumaProductSKU].
   3. **[!UICONTROL 적용]**&#x200B;을 선택합니다.

      스키마는 다음과 같아야 합니다.

      ![SKU 관계](assets/sku_relationship.png)


1. 다음에 대해 활성화: **프로필**.

1. 선택 [!UICONTROL 저장] 스키마를 저장합니다.

### 추가 스키마 만들기 {#create-additional-schemas}

다음 추가 항목 만들기 [!UICONTROL 스키마]:

| [!UICONTROL 표시 이름] | [!DNL Luma CRM Schema] | [!DNL Luma Web Events Schema] | [!DNL Luma Test Profiles schema] | [!DNL Luma Offline Purchase Events Schema] |
|  ---| ------- | ---- |----|----|
| **[!UICONTROL 클래스]** | [!UICONTROL XDM 개별 프로필] | [!UICONTROL XDM 경험 이벤트] | [!UICONTROL XDM 개별 프로필] | [IUICONTROL XDM ExperienceEvent] |
| **[!UICONTROL 기존 필드 그룹 추가]** | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details` | `Orchestration eventID`<br>`Consumer Experience Event`<br>`AEP Web SDK ExperienceEvent` | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details`<br>`Profile test details` | `Luma Identity Profile Field Group` <br>`Commerce Details` |
| **[!UICONTROL 관계]** |  | `productListItems.SKU`:<br> 참조 스키마 `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |  | `productListItems.SKU`:<br> 참조 스키마 `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |
| **[!UICONTROL 기본 ID] [!UICONTROL 네임스페이스])** | `systemIdentifier.crmId` |  | `systemIdentifier.crmId` | `systemIdentifier.LoyaltyId` |
| **[!UICONTROL 프로필 활성화]** | yes | yes | yes | yes |

## 다음 단계

데이터 구조를 만들었으므로 [데이터 세트 만들기 및 샘플 데이터 수집](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
