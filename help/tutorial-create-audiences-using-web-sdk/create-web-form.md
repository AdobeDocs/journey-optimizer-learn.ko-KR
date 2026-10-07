---
title: 웹 양식 만들기
description: HTML 페이지에서 사용자가 자신의 투자 환경 설정을 선택할 수 있는 양식을 만듭니다
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 20de8dec-aac8-43ed-8305-e723f82a5dd9
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%
---
# 웹 양식 만들기

사용자 기본 설정을 캡처하기 위해 다음 HTML 양식을 만들었습니다.
![html-form](assets/web-form.png)

사용자가 웹 페이지에서 버튼을 클릭하면 선택한 금융 환경 설정(예: 주식, 채권 또는 CD)이 캡처되어 Adobe 데이터 레이어에 푸시됩니다. 이 이벤트(assetClassSelection)는 사용자의 선택을 실시간으로 저장합니다. 그런 다음 Adobe Launch는 이 이벤트를 수신하고, 선택한 투자 옵션(PreferredFinancialInstrument)을 검색하고, 데이터를 Adobe Experience Platform(AEP)에 보내거나 개인화 규칙을 업데이트하는 등의 작업을 트리거할 수 있습니다

양식 제출을 처리하기 위해 다음 JavaScript을 작성했습니다

```javascript
function handleSubmission() {
  window.adobeDataLayer = window.adobeDataLayer || [];

  const selectedAssetClass = document.querySelector('input[name="assetclass"]:checked');
  const errorMessage = document.getElementById("error-message");
  const messageBox = document.getElementById("message");

  if (!selectedAssetClass) {
    errorMessage.textContent = "Please select a financial instrument.";
    messageBox.textContent = "";
    return;
  }

  errorMessage.textContent = "";

  const subscriptionEvent = {
    event: "assetClassSelection",
    xdm: {
      eventType: "assetClassSelection",
      eventID: "investment_preference_event",
      timestamp: new Date().toISOString(),
      FinancialInterest: {
        PreferredFinancialInstrument: selectedAssetClass.value
      }
    }
  };

  console.log("📩 Sending asset class data to AEP:", subscriptionEvent);
  window.adobeDataLayer.push(subscriptionEvent);

  // ✅ Show thank-you message
  messageBox.textContent = `Thank you for selecting "${selectedAssetClass.value}". We'll use this to personalize your experience.`;
}
```

[샘플 HTML 양식은 이 자습서의 일부로 제공됩니다](assets/webform.zip)
