---
title: 솔루션 테스트
description: 솔루션을 디버깅하는 메서드
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---

# 솔루션 테스트

구현의 유효성을 검사하려면 먼저 기본 설정 양식이 포함된 웹 페이지를 여십시오. 브라우저의 DevTools(콘솔 및 네트워크 탭)를 사용하여 양식 제출 프로세스를 모니터링합니다. 환경 설정을 제출한 후(예: &quot;Stocks&quot; 선택) AEP Web SDK(alloy.sendEvent)가 성공적으로 트리거되고 올바른 데이터가 Adobe Experience Platform으로 전송되었는지 확인합니다. AEP에서 Edge 세그멘테이션을 사용하여 대상 섹션으로 이동하고 몇 분 안에 프로필이 예상 대상(예: &quot;주식에 관심있음&quot;)에 적합한지 확인합니다. 연결된 데이터 세트에서 들어오는 이벤트 데이터를 검사하여 올바른 환경 설정 값이 포함되어 있는지 확인할 수도 있습니다. 전체 워크플로우가 제대로 작동하는지 확인하기 위해 각 자산 클래스(주식, 채권, CD)에 대해 이 프로세스를 반복합니다.

## 문제 해결 팁

프로필이 의도한 대상에 바로 적합하지 않은 경우 다음을 확인하십시오.


### Adobe 데이터 레이어 푸시 확인

* 브라우저의 개발자 도구 → 콘솔을 엽니다
* console.log(window.adobeDataLayer);
* 양식 제출 후 &quot;assetClassSelection&quot; 이벤트와 올바른 PreferredFinancialInstrument 값이 표시되는지 확인합니다.

### 실행 규칙 실행 확인

* Adobe Experience Platform Debugger(Chrome 확장) 열기
* 디버거에 로그인
* 양식 제출
* assetClassSelection에 대한 DataPushed 이벤트가 캡처되었는지 확인합니다.

다음 디버거 스크린샷이 도움이 될 것입니다.
![aep-debugger](assets/aep-debugger.png)

### ECID 가져오기

ECID(Experience Cloud ID)는 Experience Cloud 솔루션 및 세션에서 사용자를 인식하고 통합하는 데 사용되는 Adobe의 고유한 영구 식별자입니다.

* Chrome 개발자 도구 → 네트워크 탭

* &quot;interact&quot; 또는 &quot;collect&quot;로 필터링

* 양식 제출
* 응답 탭을 클릭하고 ECID를 기록합니다

![get-ecid](assets/get-ecid.png)

### 실시간 프로필 및 대상 자격 확인

* Journey Optimizer에 로그인
* 고객->프로필->찾아보기로 이동
* 스크린샷과 같이 이전 단계에서 가져온 ECID를 검색합니다
  ![ecid-profile](assets/ecid-profile.png)
* 프로필을 클릭하고 이벤트 탭을 선택하여 investment_preference_event가 나열되는지 확인합니다.
  ![events-tab](assets/profile-events.png)
* 이벤트와 관련된 json을 열고 올바른 이벤트 데이터가 포함되어 있는지 확인합니다.

### 추가 문제 해결 팁

* 스키마 및 데이터 세트 프로필이 활성화되었는지 확인합니다.
* 자격이 실시간에 가깝게 이루어지도록 대상자에 대해 Edge 세그멘테이션이 활성화되어 있는지 확인합니다.
* 특히 변경 사항을 게시한 직후 테스트하는 경우 몇 분 정도 기다린 후 대상 보기를 새로 고치는 것도 도움이 될 수 있습니다.
* 대상 규칙이 올바르게 정의되었는지 확인하고 양식 제출에서 캡처된 정확한 필드 이름과 값을 참조합니다.



