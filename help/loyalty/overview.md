---
title: Journey Optimizer 충성도 시작
description: Adobe Journey Optimizer 충성도에 온보딩하고, 문제를 구성하고, 적용하고, 표시하며, 성능을 분석하는 방법에 대해 알아봅니다.
topic: Get Started
role: User
level: Beginner
doc-type: Tutorial
jira: KT-21773
last-substantial-update: 2026-07-28T00:00:00Z
source-git-commit: 7b6c6587612fab4f027e6084c58d3fca8a5d83b0
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 43%

---


# Journey Optimizer 충성도 시작

충성도 챌린지를 사용하면 고객 행동을 유도하고 브랜드 관계를 심화하는 매력적이고 게임화된 충성도 프로그램을 만들 수 있습니다. 구매 및 리뷰 작성부터 소셜 미디어 참여 및 친구 추천에 이르기까지 특정 작업에 대해 고객에게 보상해 주는 문제를 구축하십시오.

## 충성도 소개

이 섹션에서는 Journey Optimizer Loyalty의 정의, Adobe Journey Optimizer에 적합한 위치 및 설정부터 분석까지의 과제 라이프사이클을 소개합니다.

<!--
CARDS

* https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty
  {description = Understand what Journey Optimizer Loyalty is, where it sits under AJO, and the challenge lifecycle.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Discover Journey Optimizer Loyalty">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" title="Journey Optimizer 충성도 살펴보기" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496441/?format=jpeg&nocache=1787273064899" alt="Journey Optimizer 충성도 살펴보기"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" target="_blank" rel="referrer" title="Journey Optimizer 충성도 살펴보기">Journey Optimizer 충성도 살펴보기</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer 충성도가 무엇인지, AJO에서 차지하는 위치와 과제 라이프사이클을 이해합니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## 충성도 설정

이 섹션에서는 문제 만들기를 시작하기 전에 필요한 일회성 설정에 대해 설명합니다.


<!--
CARDS

* ./set-up-loyalty/set-up-a-loyalty-reward-provider.md
  {description = Learn how to set up a reward provider, create reward definitions, and configure reward payloads so Adobe Journey Optimizer can issue loyalty rewards through your external rewards system.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up a loyalty reward provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" title="충성도 보상 제공자 설정" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497346/?format=jpeg&nocache=1787273065266" alt="충성도 보상 제공자 설정"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" target="_blank" rel="referrer" title="충성도 보상 제공자 설정">충성도 보상 공급자 설정</a>
                    </p>
                    <p class="is-size-6">Adobe Journey Optimizer이 외부 보상 시스템을 통해 충성도 보상을 발행할 수 있도록 보상 제공자를 설정하고, 보상 정의를 만들고, 보상 페이로드를 구성하는 방법에 대해 알아봅니다.</p>
                </div>
                <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## 과제 구성

이 섹션에서는 유형, 구조 및 일정, 작업 및 보상을 포함하여 충성도 과제를 만들고 구성하는 과정을 안내합니다.


<!--
CARDS

* ./configure-your-challenge/set-up-a-loyalty-challenge.md
  {description = Learn how to set up a loyalty challenge by selecting the right challenge type, configuring audiences and schedules, defining participation rules, and controlling how progress is tracked and rewarded.}
* ./configure-your-challenge/create-tasks.md
  {description = Learn how to set up tasks: purchase & spend, quantities, eligible items & exclusions, and reuse.}
* ./configure-your-challenge/configure-rewards.md
  {description = Learn how to configure rewards: provider, milestone vs. completion delivery, reward types & coupons.}
* ./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md
  {description = Learn how to use CX Enterprise Coworker to create, configure, and launch loyalty challenges using natural language, including audiences, rewards, schedules, and automated journey setup.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up a loyalty challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" title="충성도 과제 설정" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496471/?format=jpeg&nocache=1787273065480" alt="충성도 과제 설정"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" target="_blank" rel="referrer" title="충성도 과제 설정">충성도 질문 설정</a>
                    </p>
                    <p class="is-size-6">올바른 과제 유형을 선택하고, 대상과 일정을 구성하고, 참여 규칙을 정의하고, 진행 상황을 추적하고 보상받는 방식을 제어하여 충성도 과제를 설정하는 방법을 알아봅니다.</p>
                </div>
                <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create tasks for your loyalty challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/create-tasks.md" title="충성도 문제를 위한 작업 만들기" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496442/?format=jpeg&nocache=1787273065457" alt="충성도 문제를 위한 작업 만들기"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/create-tasks.md" target="_blank" rel="referrer" title="충성도 문제를 위한 작업 만들기">충성도 챌린지에 대한 작업 만들기</a>
                    </p>
                    <p class="is-size-6">구매 및 지출, 수량, 적격 품목 및 제외, 재사용 등의 작업을 설정하는 방법에 대해 알아봅니다.</p>
                </div>
                <a href="./configure-your-challenge/create-tasks.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure rewards">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/configure-rewards.md" title="보상 구성" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496481/?format=jpeg&nocache=1787273065473" alt="보상 구성"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/configure-rewards.md" target="_blank" rel="referrer" title="보상 구성">보상 구성</a>
                    </p>
                    <p class="is-size-6">보상 구성 방법: 공급자, 마일스톤 대 완료 게재, 보상 유형 및 쿠폰</p>
                </div>
                <a href="./configure-your-challenge/configure-rewards.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create a loyalty challenge and surface insights with CX Enterprise Coworker">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" title="CX Enterprise Coworker를 통해 충성도 관련 과제 및 현장 통찰력 확보" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496528/?format=jpeg&nocache=1787273065465" alt="CX Enterprise Coworker를 통해 충성도 관련 과제 및 현장 통찰력 확보"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" target="_blank" rel="referrer" title="CX Enterprise Coworker를 통해 충성도 관련 과제 및 현장 통찰력 확보">CX Enterprise Coworker를 통해 충성도 문제와 잠재 고객 인사이트 만들기</a>
                    </p>
                    <p class="is-size-6">CX Enterprise Coworker를 사용하여 대상, 보상, 일정, 자동화된 여정 설정 등 자연어를 사용하여 충성도 문제를 생성하고 구성하고 시작하는 방법에 대해 알아봅니다.</p>
                </div>
                <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## 과제 적용 및 표시

이 섹션에서는 콘텐츠 카드 및 코드 기반 경험을 사용하여 고객에게 도전하는 방법을 보여줍니다.

<!--
CARDS

* ./apply-and-display-your-challenge/build-a-challenge-content-card.md
  {description = Learn how to build a challenge content card / code-based experience, covering opt-in and dynamic progress across the opt-in, progress, and completed stages, plus rewards and channel configuration.}
* ./apply-and-display-your-challenge/display-challenge-content-using-code-based-experience-channel.md
  {description = Learn how to use code-based experiences to promote loyalty challenges, display challenge progress, and deliver personalized content within your app using HTML or JSON.}
* ./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md
  {description = Learn how to configure multi-channel messaging for every stage of a loyalty challenge, from invitations and engagement messages to completion and reward notifications.}
* ./apply-and-display-your-challenge/publish-a-challenge-and-generate-a-journey.md
  {description = Learn how to publish a challenge and automatically generate a journey. Discover how challenge communications are translated into journey orchestration, review the generated journey structure, and customize it with additional conditions, decisioning, or optimization logic.}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Build a challenge content card">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" title="과제 콘텐츠 카드 작성" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496529/?format=jpeg&nocache=1787273065807" alt="과제 콘텐츠 카드 작성"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" target="_blank" rel="referrer" title="과제 콘텐츠 카드 작성">챌린지 콘텐츠 카드 만들기</a>
                    </p>
                    <p class="is-size-6">옵트인, 진행 상황, 완료된 단계 전반에 걸친 옵트인 및 동적 진행 상황, 보상과 채널 구성을 다루는 챌린지 콘텐츠 카드/코드 기반 경험을 구축하는 방법을 알아봅니다.</p>
                </div>
                <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Display challenge content using the code-based experience channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/display-challenge-content-using-code-based-experience-channel.md" title="코드 기반 경험 채널을 사용하여 과제 콘텐츠 표시" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497465/?format=jpeg&nocache=1787273065798" alt="코드 기반 경험 채널을 사용하여 과제 콘텐츠 표시"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/display-challenge-content-using-code-based-experience-channel.md" target="_blank" rel="referrer" title="코드 기반 경험 채널을 사용하여 과제 콘텐츠 표시">코드 기반 경험 채널을 사용하여 챌린지 콘텐츠 표시</a>
                    </p>
                    <p class="is-size-6">코드 기반 경험을 사용하여 충성도 문제를 홍보하고, 과제 진행 상황을 표시하며, HTML 또는 JSON을 사용하여 앱 내에 개인화된 콘텐츠를 전달하는 방법을 알아봅니다.</p>
                </div>
                <a href="./apply-and-display-your-challenge/display-challenge-content-using-code-based-experience-channel.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up lifecycle messaging for your challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" title="문제에 대한 라이프사이클 메시지 설정" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497455/?format=jpeg&nocache=1787273065803" alt="문제에 대한 라이프사이클 메시지 설정"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" target="_blank" rel="referrer" title="문제에 대한 라이프사이클 메시지 설정">문제에 대한 라이프사이클 메시지 설정</a>
                    </p>
                    <p class="is-size-6">초대 및 참여 메시지에서 완료 및 보상 알림에 이르기까지 충성도 챌린지의 모든 단계에 대해 멀티채널 메시지를 구성하는 방법에 대해 알아봅니다.</p>
                </div>
                <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Publish a challenge and generate a journey">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/publish-a-challenge-and-generate-a-journey.md" title="과제 게시 및 여정 생성" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3498577/?format=jpeg&nocache=1787273065792" alt="과제 게시 및 여정 생성"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/publish-a-challenge-and-generate-a-journey.md" target="_blank" rel="referrer" title="과제 게시 및 여정 생성">문제를 게시하고 여정 생성</a>
                    </p>
                    <p class="is-size-6">여정을 게시하고 자동으로 게시를 생성하는 방법을 알아봅니다. 과제 커뮤니케이션이 여정 오케스트레이션으로 변환되는 방법을 알아보고, 생성된 여정 구조를 검토하고, 추가 조건, 의사 결정 또는 최적화 논리를 사용하여 이를 사용자 지정합니다.</p>
                </div>
                <a href="./apply-and-display-your-challenge/publish-a-challenge-and-generate-a-journey.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## 분석 및 보고

이 섹션에서는 충성도 문제가 발생하면 그 성과를 측정하는 방법에 대해 설명합니다.

<!--
CARDS

* ./analyze-and-report/measure-performance-with-challenge-reports.md
  {description = Learn how to use challenge reports and performance dashboards to measure participation, completion rates, revenue attribution, and overall loyalty program performance.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Measure challenge performance with challenge reports">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./analyze-and-report/measure-performance-with-challenge-reports.md" title="과제 보고서를 통해 과제 성과 측정" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497534/?format=jpeg&nocache=1787273066068" alt="과제 보고서를 통해 과제 성과 측정"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./analyze-and-report/measure-performance-with-challenge-reports.md" target="_blank" rel="referrer" title="과제 보고서를 통해 과제 성과 측정">과제 보고서를 사용하여 과제 성과 측정</a>
                    </p>
                    <p class="is-size-6">과제 보고서 및 성과 대시보드를 사용하여 참여도, 완료율, 매출 기여도 분석 및 전체 충성도 프로그램 성과를 측정하는 방법을 알아봅니다.</p>
                </div>
                <a href="./analyze-and-report/measure-performance-with-challenge-reports.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->
