---
title: 수동으로 데이터 구조 설정
description: 필요한 ID 네임스페이스를 만들고 Luma 샘플 데이터 구조를 정의합니다.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: db681243c066911af03b75f045a4dc4a990daa7d
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 7%

---

# 수동으로 데이터 설정

이 섹션에서는 필요한 ID 네임스페이스를 만들고 [!DNL Luma] 샘플 데이터 구조 만들기 [[!UICONTROL 스키마]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ko-KR-KR).

>[!TIP]
>비디오 자습서를 확인하십시오 [ID 매핑](/help/set-up-data/map-identities.md) 시작하기 전에

## 1단계: ID 네임스페이스 만들기

이 단계에서는 [!DNL Luma] 이름이 사용자 지정 ID 필드 `lumaLoyaltyId`, `lumaCrmId`, 및 `lumaProductSKU`. 동일한 네임스페이스에 있는 두 개의 일치 값을 사용하면 두 데이터 소스가 ID 그래프를 형성할 수 있으므로 ID 네임스페이스는 실시간 고객 프로필을 작성하는 데 중요한 역할을 합니다.

만들기 시작 [!UICONTROL namespace] 대상 [!DNL Luma Loyalty ID] 스키마:

1. Journey Optimizer 사용자 인터페이스에서 *로 이동합니다.**[!UICONTROL 고객]** > **[!UICONTROL ID]** 을 클릭합니다.

1. 선택 **[!UICONTROL ID 네임스페이스 만들기]**.

1. 다음 세부 정보를 제공합니다.

   | 표시 이름 | ID 기호 | 유형 |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL 교차 장치 ID] |

1. **[!UICONTROL 만들기]**&#x200B;를 선택합니다.

   ![네임스페이스 만들기](assets/createNamespace.png)

1. 동일한 단계에 따라 네임스페이스를 두 개 더 만듭니다.

   | 표시 이름 | ID 기호 | 유형 |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL 교차 장치 ID] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL 비사용자 식별자] |

## 2단계: 스키마 만들기

이 단계에서는 6개를 만들어 샘플 데이터의 구조를 정의합니다 [[!UICONTROL 스키마]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events]](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

>[!TIP]
>
>비디오 자습서를 확인하십시오. [스키마 만들기](/help/set-up-data/create-schema.md) 시작하기 전에

### 만들기 [!DNL Luma Loyalty] [!UICONTROL 스키마] {#create-luma-loyalty-schema}

#### 스키마 만들기

만들기 시작 [!DNL Luma Loyalty] 스키마:

1. 이동 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 스키마]** 을 클릭합니다.

1. 선택 **[!UICONTROL 스키마 만들기]** 오른쪽 위에 있습니다.

1. 드롭다운 메뉴에서 을(를) 선택합니다 **[!UICONTROL XDM 개별 프로필]**, 개별 고객(지점, 상태 등)의 속성을 모델링하므로

   ![스키마 만들기](assets/loyaltyCreateSchema.png)

#### 기존 필드 그룹 추가

다음으로 스키마에 필드 그룹을 추가하라는 메시지가 표시됩니다. 그룹을 사용하여 스키마에 모든 필드를 추가해야 합니다. 기존 필드 그룹을 추가하고 있으므로 필드 그룹을 만들어야 합니다.

>[!NOTE]
>
>만약 [!UICONTROL 필드 그룹] 모달이 [!UICONTROL 스키마] 페이지를 선택하고 **[!UICONTROL 추가]** (다음 이미지에 표시된 대로).

![필드 그룹 추가](assets/add_field_group.png)

1. 설정 **[!UICONTROL 필드 그룹 추가]** 페이지에서 다음 필드 그룹을 활성화합니다.

   * **[!UICONTROL 인구 통계 세부 정보]** 이름 및 생년월일과 같은 기본 고객 데이터의 경우.

   * **[!UICONTROL 개인 연락처 세부 정보]** 전자 메일 주소 및 전화 번호와 같은 기본 연락처 세부 사항에 대해 설명합니다.

   * **[!UICONTROL 충성도 세부 사항]** 포인트, 가입 날짜 또는 상태와 같은 충성도 세부 사항에 대해 설명합니다. 충성도 필드 그룹이 목록 맨 아래에 있으므로 검색하는 것이 더 쉽습니다.

1. 선택 **[!UICONTROL 필드 그룹 추가]** 세 필드 그룹을 모두 스키마에 추가하려면

   ![표준 필드 그룹 선택](assets/addstandardFieldGroups.png)

1. 스키마의 맨 위 노드를 선택합니다.

1. Enter 키 `Luma Loyalty Schema` 로서의 [!UICONTROL 표시 이름].

#### 만들기 [!UICONTROL 필드 그룹]

스키마 간에 일관성을 유지하기 위해 Adobe은 단일 그룹에서 모든 시스템 식별자를 관리하는 것을 권장합니다.

1. 에서 **[!UICONTROL 조성물]** 섹션 [!UICONTROL 필드 그룹], 선택 **[!UICONTROL 추가]**.

1. 선택 **[!UICONTROL 새 필드 그룹 만들기]**.

1. 추가 `Luma Identity Profile Field Group` 로서의 **[!UICONTROL 표시 이름]**.

1. 추가 `system identifiers for XDM Individual Profile class` 로서의 **[!UICONTROL 설명]**.

1. 선택 **[!UICONTROL 필드 그룹 추가]**.

   ![새 필드 그룹 만들기](assets/addnewfieldgroup.png)

#### 새 필드에 필드 추가 [!UICONTROL 필드 그룹]

새로운 빈 필드 그룹이 스키마에 추가됩니다. + 단추를 사용하여 계층의 모든 위치에 새 필드를 추가할 수 있습니다. 이 경우 루트 수준에서 필드를 추가해야 합니다.

1. 선택 **[!UICONTROL +]** 스키마 이름 옆에 표시됩니다.

   이 단계에서는 **테넌트 id** 네임스페이스 를 사용하여 사용자 지정 필드와 표준 필드 간의 충돌을 관리합니다.

1. 에서 **[!UICONTROL 필드 속성]** 사이드바에서 새 필드의 세부 사항을 추가합니다.

   * **필드 이름:** `systemIdentifier`

   * **[!UICONTROL 표시 이름]:** `System Identifier`

   * **유형:** 개체

   * **[!UICONTROL 필드 그룹 할당]:** [!DNL Luma identifiers]

1. 선택 **[!UICONTROL 적용]**.

   ![시스템 식별자 추가](assets/addsysteidentifier.png)

   아래에 두 개의 필드를 추가합니다 `systemIdentifier` 개체:

   | [!UICONTROL Fieldname] | [!UICONTROL 표시 이름] | [!UICONTROL 유형] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty ID` | [!UICONTROL 문자열] |
   | `crmId` | `CRM Id` | [!UICONTROL 문자열] |

![필드](./assets/add_fields.png)

#### ID 설정

이제 [!UICONTROL namespace] 그리고 [!DNL Luma Loyalty schema] 구성했습니다. 데이터를 수집하려면 먼저 ID 필드에 레이블을 지정해야 합니다. 에 사용되는 각 스키마 [!UICONTROL 실시간 고객 프로필] 는 기본 ID를 지정해야 하며 수집된 각 레코드에는 해당 필드에 대한 값이 있어야 합니다.

1. 설정 **기본 ID**:

   에서 **[!DNL Luma Loyalty Schema]**:

   1. **[!DNL Luma Identity Profile Field Group]**&#x200B;을(를) 선택합니다.

   2. 을(를) 선택합니다 **[!DNL loyaltyId]** 필드.

   3. 에서 **[!UICONTROL 필드 속성]**&#x200B;를 활성화하십시오. **[!UICONTROL ID]** 상자.

   4. 를 활성화합니다 **[!UICONTROL 기본 ID]** 상자.

   5. 을(를) 선택합니다 `Luma Loyalty Id` 네임스페이스 **[!UICONTROL ID 네임스페이스]** 드롭다운.

   6. 선택 **[!UICONTROL 적용]**.

      ![기본 ID](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. 설정 **보조 ID**:

   에서 **[!DNL Luma Loyalty Schema]**:

   1. 을(를) 선택합니다 **[!DNL Luma Identity Profile Field Group]**..

   2. 을(를) 선택합니다 `crmId` 필드.

   3. 에서 **[!UICONTROL 필드 속성]**&#x200B;를 활성화하십시오. **[!UICONTROL ID]** 상자.

   4. 을(를) 선택합니다 `Luma CRM Id` 네임스페이스 **[!UICONTROL ID 네임스페이스]** 드롭다운.

   5. 선택 **[!UICONTROL 적용]**.

#### 프로필 활성화 및 스키마 저장

1. 스키마의 맨 위 노드를 선택합니다.

1. 에서 [!UICONTROL 필드 속성] 활성화 **[!UICONTROL 프로필]**.

   스키마는 다음과 같습니다.

   ![Luma 충성도 스키마](assets/lumaloyaltyschema.png)

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

### 만들기 [!DNL Luma Product catalog Schema] {#create-luma-product-catalog-schema}

1. 이동 [!UICONTROL 데이터 관리] -> **[!UICONTROL 스키마]** 을 클릭합니다.

1. 을(를) 선택합니다 **[!UICONTROL 스키마 만들기]** 오른쪽 위에 있는 단추입니다.

1. 드롭다운 메뉴에서 을(를) 선택합니다 **[!UICONTROL 모든 스키마 유형 찾아보기]**&#x200B;를 사용하여 클래스를 만들 수 있습니다.

1. 선택 **[!UICONTROL 새 클래스 만들기].

1. 표시 이름을 추가합니다. `Luma Product Catalog Class`.

1. 클래스를 할당합니다.

1. 만들기 [!UICONTROL 필드 그룹]:

   * 표시 이름: `Luma Product Catalog Field Group`

1. 다음 필드를 **[!DNL Luma Product Catalog Field Group]**.

   * 필드 이름: `product`

   * 표시 이름: `Product`

   * 유형: [!UICONTROL 개체]

   * 필드 그룹: [!DNL Luma Product Catalog Field Group]

1. 선택 **[!UICONTROL 적용]**.

1. 다음 필드를 **[!DNL Product]** 개체:

   | [!UICONTROL Fieldname] | [!UICONTROL 표시 이름] | [!UICONTROL 유형] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL 문자열] |
   | `name` | `Name` | [!UICONTROL 문자열] |
   | `category` | `Category` | [!UICONTROL 문자열] |
   | `color` | `Color` | [!UICONTROL 문자열] |
   | `size` | `Size` | [!UICONTROL 문자열] |
   | `price` | `Price` | [!UICONTROL 이중] |
   | `description` | `Description` | [!UICONTROL 문자열] |
   | `ImageURL` | `Image URL` | [!UICONTROL 문자열] |
   | `stockQuantity` | `Stock Quantity` | [!UICONTROL 문자열] |

1. 설정 **[!DNL SKU]** 기본 ID
1. 추가 **[!UICONTROL 표시 이름]** `Luma Product Catalog Field Group` 변환 후 [!UICONTROL 필드 그룹].

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.


### 만들기 [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}


1. 이동 **[!UICONTROL 데이터 관리]** -> **[!UICONTROL 스키마]** 을 클릭합니다.

1. 을(를) 선택합니다 **[!UICONTROL 스키마 만들기]** 오른쪽 위에 있는 단추입니다.

1. 드롭다운 메뉴에서 을(를) 선택합니다 **[!UICONTROL 모든 스키마 유형 찾아보기]**.

1. 선택 **[!UICONTROL 새 클래스 만들기]**.

1. 표시 이름을 추가합니다. `Luma Business Event Class`.

1. 유형 선택: *[!UICONTROL 시계열]*.

1. 클래스를 할당합니다.

1. 만들기 [!UICONTROL 필드 그룹]:

   * 표시 이름: `Luma Product Inventory Event Details Field Group`

1. 추가 **[!UICONTROL 표시 이름]** `Luma Product Inventory Event Schema` 를 스키마 로 전환합니다.

1. 다음 필드를 **[!DNL Luma Product Inventory Event Details Field Group]**:

   * 필드 이름: `inventoryEvent`

   * 표시 이름: `Inventory Event`

   * 유형: [!UICONTROL 개체]

   * 필드 그룹: `Luma Product Inventory Event Details Field Group`

1. 다음 필드를 `Product Inventory Event Details` 개체:

   | [!UICONTROL Fieldname] | [!UICONTROL 표시 이름] | [!UICONTROL 유형] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL 문자열] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL 문자열] |

   1. 를 `stockEventType` 열거하려면 유형을 선택합니다. `string`.

   2. 아래쪽으로 스크롤합니다. **[!UICONTROL 필드 속성]**.

   3. 활성화 **[!UICONTROL 열거형]**.

   4. Enter 키 **[!UICONTROL 값] ([!UICONTROL label)]**: `restock` (`restock`).

   5. 선택 **[!UICONTROL 행 추가]**.

   6. Enter 키 **[!UICONTROL 값] ([!UICONTROL label)]**: `outOfStock` (`out of stock`).

   7. 선택 **[!UICONTROL 적용]**.

      ![enum](assets/enum.png)

1. 설정 `productId` 필드 **[!UICONTROL 기본 ID]** 사용 **[!DNL Luma Product namespace]**.

1. 을(를) 선택합니다 `sku` 필드 및 `product.sku` 의 필드 **[!DNL Luma Product catalog Schema]** 스키마:

   1. 아래쪽으로 스크롤합니다. **[!UICONTROL 필드 속성]**.

   2. 활성화 **[!UICONTROL 관계]**.

      1. **[!UICONTROL 참조 스키마]**: [!DNL Luma Product catalog Schema].

      2. **[!UICONTROL 참조 ID 네임스페이스]**: [!DNL Luma Product].
   3. 선택 **[!UICONTROL 적용]**.

      스키마는 다음과 같습니다.

      ![SKU 관계](assets/sku_relationship.png)


1. 사용 **프로필**.

1. 선택 [!UICONTROL 저장] 스키마를 저장하려면 을 클릭합니다.

### 만들기 [!DNL Luma CRM] 및 [!DNL Luma Product Interactions] 스키마 {#create-luma-crm-and-luma-product-interactions-schemas}

다음을 추가로 만듭니다 [!UICONTROL 스키마]:

| [!UICONTROL 표시 이름] | [!DNL Luma CRM] | [!DNL Luma Product Interactions] | [!DNL Luma Test Profiles] |
|  ---| ------- | ---- |----|
| **[!UICONTROL 유형]** | [!UICONTROL XDM 개별 프로필] | [!UICONTROL XDM 경험 이벤트] | [!UICONTROL XDM 개별 프로필] |
| **[!UICONTROL 기존 필드 그룹 추가]** | Luma 식별자<br>인구 통계 세부 정보<br>개인 연락처 세부 정보 | ID 맵<br>상거래 세부 사항 | Luma 식별자<br>인구 통계 세부 정보<br>개인 연락처 세부 정보<br>프로필 테스트 세부 사항 |
| **[!UICONTROL 관계]** |  | *[!DNL productListItems.SKU]*:<br> 참조 스키마 *[!DNL Luma Product catalog Schema]* <br>[!DNL Reference identity namespace] *[!DNL Luma Product]* 스키마 |
| **[!UICONTROL 기본 ID] [!UICONTROL namespace])** | systemIdentifier.crmId<br>(Luma CRM Id) |  | personalEmail.address<br>(Email) |
| **[!UICONTROL 보조 ID] [!UICONTROL namespace]** | personalEmail.address(이메일)<br>mobilePhone.number(전화) |  |
| **[!UICONTROL 프로필에 사용]** | yes | yes | yes |

## 다음 단계

이제 데이터 구조를 만들었으므로 [데이터 세트 만들기 및 샘플 데이터 수집](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
