---
title: Journey Optimizer 과제 - 소개 및 사전 요구 사항
description: 여정 캔버스에서 여정을 작성하는 기본적인 방법을 이해합니다.
feature: Journeys
role: Admin
level: Beginner
hide: true
source-git-commit: dd2832c1e99ed9b8407a0aa9356335d3bce40622
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 7%

---


# Journey Optimizer 과제 - 소개 및 사전 요구 사항

![AJO Challents 배너](./assets/ajo-banner-challenges.png)

도전이란 시나리오 및 학습한 내용을 실행하는 데 필요한 요구 사항을 제공합니다. 당면 과제는 기술 수준을 평가하고 기술 격차를 파악하는 데 도움이 됩니다.

이 섹션의 각 과제에서는 구현할 고유한 사용 사례를 다룹니다. 타겟 대상(성향) 및 필요한 기술은 각 과제의 시작 부분에 나열되어 있습니다.

## 전제 조건

### 시스템 요구 사항

* Journey Optimizer 샌드박스 액세스
* 전용 교육 샌드박스에서 이 문제를 완료하는 것이 좋습니다. 자세한 내용은 [교육 샌드박스 자습서 설정](https://experienceleague.adobe.com//docs/journey-optimizer-learn/configure-a-training-sandbox/introduction-and-prerequisites.html) 참조하십시오.
* 다음 액세스 권한이 필요합니다.
   * *여정 관리자* 또는 *여정 관리자* 권한
   * 테스트 프로필 및 해당 속성 보기
* 인스턴스에 대해 AEM Assets Essentials를 프로비저닝해야 합니다
* 전자 메일 채널은 트랜잭션 및 마케팅 메시지용으로 구성해야 합니다

>[!NOTE]
> 이 연습은 Luma 샘플 데이터를 기반으로 개발되었습니다. 샘플 데이터로 구성된 교육 샌드박스를 설정하는 것이 좋습니다. 자습서를 방문하십시오 [Adobe Experience Platform으로 샘플 데이터 가져오기](https://experienceleague.adobe.com/docs/platform-learn/tutorials/import-sample-data.html?lang=en) 자세한 지침

### 필수 작업

* Adobe Journey Optimizer을 처음 사용하는 경우 교육 과정을 완료합니다 [여정 관리자 및 관리자를 위한 Journey Optimizer 시작하기](https://experienceleague.adobe.com/?recommended=JourneyOptimizer-U-1-2021.1).
* 시작하기 전에 [luma-assets.zip](/help/challenges/assets/email-assets/luma-assets.zip) 파일. 이 파일에는 문제를 해결하는 데 필요한 모든 자산이 포함되어 있습니다
* 다운로드 폴더에서 `luma-assets.zip` 파일을 컴퓨터의 원하는 위치에 저장하고 압축을 해제합니다.

## 더 스토리

Luma는 여러 국가에 있는 상점, 웹 사이트를 통한 온라인 콘텐츠 및 모바일 앱을 보유한 가상의 스포츠 의류 회사입니다. Luma는 Adobe Journey Optimizer을 사용하여 고객에게 연결되고 상황에 맞는 개인화된 경험을 제공합니다.

Luma는 최신 의류 및 기어 컬렉션을 홍보하고 기존 고객을 위한 판매를 유도하려고 합니다. Journey Optimizer에서 Luma 마케팅 및 유지 캠페인을 구현하기 위해 고용된 것입니다.

## 당면 과제

<table>
<tr>
<td>
 <div>
      <a href="summer-collection-announcement-challenge.md">
        <img alt="여름 컬렉션 발표용 이미지" src="./assets/email-assets/luma-transactional-onboarding-3.png"/>
      </a>
      </div>
  </td>
  <td>
   <a href="summer-collection-announcement-challenge.md">
    <strong>여름 컬렉션 공지 만들기 </strong>
    </a>
      <p>
      <em>새로운 Luma 여름 컬렉션을 홍보합니다. </em>
      <p>
      <b>필요한 기술:</b>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html"> 세그먼트 만들기</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html">HTML 이메일 콘텐츠 가져오기 및 작성</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html">사용 사례 - 세그먼트 읽기</li>
  </td>
  </tr>
  <tr>
  <td>
  <div>
    <a href="order-confirmation-challenge.md">
      <img alt="Luma 이메일" src="./assets/email-assets/luma-transactional-order-confirmation.png"/>
    </a>
  </td>
  <td>
      <a href="order-confirmation-challenge.md">
    <strong>주문 확인 만들기</strong>
    </a>
    <div>
    <p>
    <em>누군가 온라인 구매를 완료하면 주문 확인 이메일을 보냅니다
    </em>
    <p>
  </td>
  </tr>
  <tr>
    <td>
    <div>
    <a href="product-replenishment-challenge.md">
      <img alt="Luma 웹 사이트" src="./assets/email-assets/luma-ProductReplenishment.jpg"/>
    </a>
    </div>
    <td>
    <div >
      <a href="product-replenishment-challenge.md">
    <strong>제품 보충 통지 생성 </strong>
    </a>
    </div>
    <p>
    <em>이전에 재고 부족 항목이 다시 재고가 있는 경우 고객에게 알립니다.</em>
    <p>
  </td>
  </tr>
  <tr>
    <td>
    <div>
    <a href="loyalty-status-welcome-email-challenge.md">
      <img alt="시작" src="./assets/email-assets/luma-transactional-onboarding-1.png"/>
    </a>
    </div>
    <td>
    <div >
      <a href="loyalty-status-welcome-email-challenge.md">
    <strong>충성도 상태 시작 이메일 만들기 </strong>
    </a>
    </div>
    <p>
    <em>충성도 고객이 새로운 계층으로 이동하여 새로운 혜택을 축하하고 알려주면 e-메일을 보냅니다</em>
    <p>
  </td>
  </tr>
</table>