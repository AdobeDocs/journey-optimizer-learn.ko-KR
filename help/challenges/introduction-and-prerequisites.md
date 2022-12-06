---
title: Journey Optimizer 과제 - 소개 및 사전 요구 사항
description: 여정 캔버스에서 여정을 작성하는 기본적인 방법을 이해합니다.
feature: Journeys
role: Admin
level: Beginner
hide: true
exl-id: 87a79560-c098-4e72-abec-6b750ec730ee
source-git-commit: e148101f8404c8e2019ee17823bcf1d7a9668bc5
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 12%

---

# Journey Optimizer 과제 - 소개 및 사전 요구 사항

![AJO Challents 배너](./assets/ajo-banner-challenges.png)

도전이란 시나리오 및 학습한 내용을 실행하는 데 필요한 요구 사항을 제공합니다. 당면 과제는 기술 수준을 평가하고 기술 격차를 파악하는 데 도움이 됩니다.

이 섹션의 각 과제에서는 구현할 고유한 사용 사례를 다룹니다. 타겟 대상(성향) 및 필요한 기술은 각 과제의 시작 부분에 나열되어 있습니다.

## 전제 조건

### 시스템 요구 사항

* Journey Optimizer 샌드박스 액세스 - 전용 교육 샌드박스에서 이 과제를 완료하는 것이 좋습니다.
* 인스턴스에 대해 AEM Assets Essentials를 프로비저닝해야 합니다
* 전자 메일 채널은 트랜잭션 및 마케팅 메시지용으로 구성해야 합니다

### 액세스 권한

다음 액세스 권한이 필요합니다.
* *여정 관리자* 또는 *여정 관리자*
* 테스트 프로필 및 해당 속성 보기

>[!NOTE]
> 이 연습은 Luma 샘플 데이터를 기반으로 개발되었습니다. 샘플 데이터로 구성된 교육 샌드박스를 설정하는 것이 좋습니다. 자습서를 방문하십시오 [교육 샌드박스 구성](/help/tutorial-configure-a-training-sandbox/introduction-and-prerequisites.md) 자세한 지침은

### 필수 작업

* Adobe Journey Optimizer을 처음 사용하는 경우 교육 과정을 완료합니다 [여정 관리자 및 관리자를 위한 Journey Optimizer 시작하기](https://experienceleague.adobe.com/?recommended=JourneyOptimizer-U-1-2021.1).


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
   <strong><a href="summer-collection-announcement-challenge.md">여름 컬렉션 공지 만들기 </strong>
    </a>
      <p>
      <em>기존 고객의 세그먼트에 여름 컬렉션 공지 이메일을 보내는 여정을 만듭니다. </em>
      <p>
      <b>필요한 기술:</b>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html"> 세그먼트 만들기</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html">HTML 이메일 콘텐츠 가져오기 및 작성</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html">사용 사례 - 세그먼트 읽기</li>
  </td>
  </tr>
   <tr>
    <td>
    <div>
    <a>
      <img alt="시작" src="./assets/email-assets/luma-transactional-onboarding-1.png"/>
    </a>
    </div>
    <td>
    <div >
      <a>
    <strong>충성도 상태 시작 이메일 만들기(준비 중) </strong>
    </a>
    </div>
    <p>
    <em>충성도 고객이 새로운 계층으로 이동하여 새로운 혜택을 축하하고 알려주면 e-메일을 보냅니다</em>
    <p>
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
    <strong><a href="order-confirmation-challenge.md">주문 확인 만들기</strong>
    </a>
    <div>
    <p>
    <em>트랜잭션 메시지를 만들고 개인화하는 방법에 대한 지식을 테스트합니다
    </em>
    <p>
    <b>필요한 기술:</b>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html"> 메시지 편집기로 이메일 콘텐츠 만들기</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html">개인화에 컨텍스트 기반 이벤트 정보 사용</li>
      <li><a href="https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en">개인화에 도우미 기능 사용</li>
  </td>
</table>
