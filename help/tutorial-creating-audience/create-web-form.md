---
title: 웹 양식 만들기
description: HTML 페이지에서 사용자가 자신의 투자 환경 설정을 선택할 수 있는 양식을 만듭니다
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '123'
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
