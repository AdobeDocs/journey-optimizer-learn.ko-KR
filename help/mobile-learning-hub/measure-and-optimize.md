---
title: 성능 측정 및 최적화
description: 보고서에 액세스하고, 성과를 분석하고, 더 나은 결과를 위한 전략을 세웁니다.
feature: Reporting, Governance, Privacy
role: User
level: Beginner, Intermediate
hide: false
index: true
jira: KT-19871
last-substantial-update: 2025-12-18T00:00:00.000Z
exl-id: fb06f781-3370-4825-a815-14ef33ad2322
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a9f73820-6899-47c2-a597-3fec28ab756a
    internal-label: Reporting
  - id: 9bb0ff1a-29d5-5edf-a6a2-8ec9c30e28c8
    internal-label: Privacy
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
    internal-label: Data management activity
subfeature_v2:
  - id: f2c0f677-2df6-47f0-a531-ae6a5aa47f37
    internal-label: Governance
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 87%
---
# 성능 측정 및 최적화

보고서에 액세스하고, 성과를 분석하고, 더 나은 결과를 위한 전략을 세웁니다.

1. 게재, 열기, 클릭 수 및 전환과 같은 주요 지표를 추적합니다.
2. 대상 성과를 분석하여 참여 패턴을 파악합니다.
3. 데이터 통찰력을 기반으로 메시지 타이밍, 콘텐츠 및 타겟팅을 구체화합니다.

<!--
CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/report-and-monitor/measurement-and-reporting-overview
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/report-and-monitor/channel-level-reports
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/report-and-monitor/enhanced-reporting-with-customer-journey-analytics
{description = Journey Optimizer reporting is now fully integrated with Customer Journey Analytics capabilities, standardizing reporting across both platforms and improving data consistency and reliability. This seamless integration between Journey Optimizer and Customer Journey Analytics provides a clearer view of performance metrics, enabling users to make more informed decisions.}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Measurement & Reporting - Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/measurement-and-reporting-overview" title="측정 및 보고 - 개요" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3432673/?format=jpeg&nocache=1755729019661" alt="측정 및 보고 - 개요"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/measurement-and-reporting-overview" target="_blank" rel="referrer" title="측정 및 보고 - 개요">측정 및 보고 - 개요</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer의 보고 기능에 대해 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/measurement-and-reporting-overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Channel level reports">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/channel-level-reports" title="채널 수준 보고서" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3424537/?format=jpeg&nocache=1755729019635" alt="채널 수준 보고서"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/channel-level-reports" target="_blank" rel="referrer" title="채널 수준 보고서">채널 수준 보고서</a>
                    </p>
                    <p class="is-size-6">채널 수준에서 보고서에 액세스하고, 탐색하고, 내보내는 방법에 대해 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/channel-level-reports" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Enhanced reporting with Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/enhanced-reporting-with-customer-journey-analytics" title="Customer Journey Analytics를 통한 향상된 보고 기능" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3430413/?format=jpeg&nocache=1755729019655" alt="Customer Journey Analytics를 통한 향상된 보고 기능"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/enhanced-reporting-with-customer-journey-analytics" target="_blank" rel="referrer" title="Customer Journey Analytics를 통한 향상된 보고 기능">Customer Journey Analytics를 통한 향상된 보고 기능</a>
                    </p>
                    <p class="is-size-6">이제 Journey Optimizer의 보고 기능이 Customer Journey Analytics 기능과 완전히 통합되어 양 플랫폼의 보고를 표준화하고 데이터의 일관성과 안정성을 개선합니다. 이렇게 Journey Optimizer와 Customer Journey Analytics가 원활하게 통합됨으로써 사용자가 성과 지표를 보다 명확하게 확인하여 확실한 정보에 근거한 결정을 내릴 수 있습니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/report-and-monitor/enhanced-reporting-with-customer-journey-analytics" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->
