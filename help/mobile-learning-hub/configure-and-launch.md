---
title: 구성 및 실행
description: Adobe Journey Optimizer(AJO) 및 Adobe Experience Platform(AEP)에서 모바일 채널을 구성하고, 모바일 앱과 통합하고, 마케팅 캠페인 실행에 대한 준비를 확인합니다.
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: 95c0db8571e13c4f6e3cf2933022d0535192dd5d
workflow-type: tm+mt
source-wordcount: '2106'
ht-degree: 18%

---


# 구성 및 실행

**관리자** 및 **모바일 앱 개발자**&#x200B;를 위해 이 섹션에서는 Adobe Journey Optimizer에서 모바일 및 웹 채널을 구성하고 시작하는 방법을 보여줍니다. 사전 요구 사항, 권한 및 플랫폼 지원에 대해 설명한 다음 앱별 구성을 만드는 과정을 안내합니다.

>[!IMPORTANT]
>
> Journey Optimizer 및 Experience Platform을 처음 사용하는 경우 다음 과정을 통해 Journey Optimizer의 데이터 관리 핵심 개념에 대해 숙지하십시오. [Adobe Journey Optimizer에서 지능형 여정 활성화를 위한 데이터 엔지니어](https://experienceleague.adobe.com/en/courses/ajo-engineer-data-for-intelligent-journey-activation){target="_blank"}
>


## Adobe Journey Optimizer의 모바일 기능

푸시 메시지, 인앱 메시지 및 콘텐츠 개인화를 포함하여 Adobe Journey Optimizer이 개발자, 마케터 및 제품 팀을 위해 제공하는 모바일 기능을 이해합니다.

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## 채널 구성

### 모바일 푸시 및 인앱

Journey Optimizer의 모바일 구현은 앱에서 **Adobe Experience Platform Mobile SDK** 통합으로 시작합니다. SDK는 데이터 수집과 Adobe Experience Platform(AEP) 및 Adobe Journey Optimizer(AJO)과 같은 해당 애플리케이션과의 상호 작용에 필수적입니다.

#### Mobile SDK 소개:

모바일 SDK:

- 앱 이벤트(화면 보기, 탭, 구매, 라이프사이클 이벤트 등)를 수집하여 **Adobe Experience Platform Edge Network**&#x200B;로 보냅니다.
- Journey Optimizer에서 고객 프로필을 안전하게 빌드하고 사용할 수 있도록 **ID** 및 **동의**&#x200B;를 관리합니다.
- **푸시 토큰**&#x200B;을 등록 및 업데이트하고 **푸시 및 인앱 추적 이벤트**&#x200B;를 다시 Adobe Experience Platform으로 보냅니다.
- 메시지를 끝까지 전달, 렌더링 및 측정할 수 있도록 **[Journey Optimizer mobile extension](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer)**&#x200B;과 통합됩니다.

모바일 SDK을 앱에 통합하지 않으면 Journey Optimizer에서 안정적으로 다음을 수행할 수 없습니다.

- 모바일 푸시 및 인앱 메시지를 전달하고 추적합니다.
- 콘텐츠 카드를 렌더링하고 추적합니다.
- 실시간 인앱 비헤이비어를 사용하여 여정을 트리거하고 경험을 개인화할 수 있습니다.

#### 새로운 구현을 위한 가이드 채널 설정

새로운 모바일 인앱 및 푸시 구현의 경우 가이드 채널 설정이 권장되는 시작점입니다. 잘못 구성된 데이터스트림 또는 확장 누락의 위험을 줄이고 Assurance을 통한 SDK 유효성 검사를 안내합니다.

>[!PREREQUISITES]
>
>다음을 수행해야 합니다.
>
> - 조직에 대해 **Adobe Journey Optimizer**(AJO)이(가) 프로비저닝되었습니다.
> - [데이터 수집 및 Journey Optimizer 권한을 사용하여 Adobe Experience Platform 액세스](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config#:~:text=Required%20permissions).
> - 채널 및 구성 설정에 대한 AJO의 관리자 권한.
> - 모바일 앱의 소스 코드(iOS, Android 또는 크로스 플랫폼 프레임워크)에 액세스합니다.
> - 앱에서 필수 OS 수준 기능(예: 푸시 권한, 알림 서비스 확장, 백그라운드 모드)이 활성화되어 있습니다.
> - 기존 구성 옵션을 사용하는 경우 [최신 Adobe Experience Platform Mobile SDK 버전](https://developer.adobe.com/client-sdks/home/current-sdk-versions/){target="_blank"}을 사용하고 있는지 확인하십시오


>[!VIDEO](https://video.tv.adobe.com/v/3433053/?learn=on)

자세한 내용은 [안내 채널 설정 시작](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config.html?lang=ko){target="_blank"}을 참조하세요.


#### 푸시 채널의 수동 구성

다음 안내서에서는 데이터 흐름을 이해하고 Firebase 및 Apple 푸시 알림 서비스(APNs)와 같은 서비스와 통합하는 것부터 모바일 앱 설정 및 알림 테스트에 이르기까지 푸시 알림을 수동으로 구성하고 효과적으로 사용하는 데 필요한 모든 사항을 안내합니다.

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs
{title = Push notification data flow and components}
{description = Learn how to setup and understand key services and workflows involved with push notifications in Journey Optimizer.}
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=2000&format=webply&optimize=medium}
{target = _blank}

* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=2000&format=webply&optimize=small}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview 
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification data flow and components">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" title="푸시 알림 데이터 흐름 및 구성 요소" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=400&format=webply&optimize=medium" alt="푸시 알림 데이터 흐름 및 구성 요소"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" title="푸시 알림 데이터 흐름 및 구성 요소">푸시 알림 데이터 흐름 및 구성 요소</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer의 푸시 알림과 관련된 주요 서비스 및 워크플로를 설정하고 이해하는 방법에 대해 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">자세히 알아보기</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification configuration">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" title="푸시 알림 구성" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=400&format=webply&optimize=medium" alt="푸시 알림 구성"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" title="푸시 알림 구성">푸시 알림 구성</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer을 사용하여 푸시 알림을 전송하도록 환경을 구성하는 방법 알아보기</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">자세히 알아보기</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" title="모바일 앱에서 Adobe Experience Cloud 구현 자습서" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="모바일 앱에서 Adobe Experience Cloud 구현 자습서"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="모바일 앱에서 Adobe Experience Cloud 구현 자습서">모바일 앱에서 Adobe Experience Cloud 구현 튜토리얼</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Cloud 모바일 애플리케이션을 구현하는 방법을 알아봅니다. 이 튜토리얼에서는 샘플 Swift 또는 Android 앱에서의 Experience Cloud 애플리케이션 구현을 안내합니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">자세히 알아보기</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### 추가 리소스


<!-- CARDS
* https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk
{target = _blank}
* https://developer.adobe.com/client-sdks/home/base/assurance
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Get the Adobe Experience Platform Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" title="Adobe Experience Platform Mobile SDK 가져오기" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Adobe Experience Platform Mobile SDK 가져오기"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" title="Adobe Experience Platform Mobile SDK 가져오기">Adobe Experience Platform Mobile SDK 가져오기</a>
                    </p>
                    <p class="is-size-6">애플리케이션에 Adobe Experience Platform Mobile SDK을 설치하는 방법을 설명하는 안내서입니다.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">자세히 알아보기</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Assurance overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/base/assurance" title="Adobe Experience Platform Assurance 개요" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Adobe Experience Platform Assurance 개요"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" title="Adobe Experience Platform Assurance 개요">Adobe Experience Platform Assurance 개요</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Platform Assurance 모바일 확장 기능에 대한 개요입니다.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">자세히 알아보기</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### 모바일 SDK 준비 체크리스트

앱을 마케터에게 전달하기 전에 **[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/){target="_blank"}**&#x200B;에서 다음을 확인하십시오.

>[!SUCCESS]
> 
> [ ] 코어 SDK + Journey Optimizer 확장이 로드됨,\
> [ ]개의 이벤트가 올바른 데이터 스트림 및 데이터 세트에서 흐르고 있습니다.\
> [ ]ID와 동의가 모든 주요 이벤트에 있습니다.\
> [ ]개의 푸시 토큰 및 상호 작용이 추적되고\
> [ ] 하나 이상의 테스트 인앱 메시지 또는 콘텐츠 카드가 표시되었으며 노출로 기록되었습니다.


### 콘텐츠 카드

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp
{title = Configure content cards support in Mobile SDK}
{description = Learn how to integrate content cards in your mobile application using Messaging SDK.}
{image = https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=2000&format=webply&optimize=medium}
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure content cards support in Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" title="Mobile SDK에서 콘텐츠 카드 지원 구성" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp./media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=400&format=jpg&optimize=medium" alt="Mobile SDK에서 콘텐츠 카드 지원 구성"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" title="Mobile SDK에서 콘텐츠 카드 지원 구성">모바일 SDK에서 콘텐츠 카드 지원 구성</a>
                    </p>
                    <p class="is-size-6">메시징 SDK을 사용하여 모바일 애플리케이션에서 컨텐츠 카드를 통합하는 방법을 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">자세히 알아보기</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### WhatsApp

**WhatsApp 채널**&#x200B;을 구성하는 방법을 이해합니다.

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="WhatsApp 채널 설정" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1765241811878" alt="WhatsApp 채널 설정"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="WhatsApp 채널 설정">WhatsApp 채널 설정</a>
                    </p>
                    <p class="is-size-6">이 튜토리얼에서는 Adobe Journey Optimizer에서 WhatsApp 채널을 설정하여 실시간 비즈니스 메시지를 활성화하는 방법을 설명합니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

표준 공급자(Twilio, Synch 또는 Infobip)를 사용하거나 사용자 지정 SMS 공급자를 사용하여 **SMS/MMS/RCS 채널**&#x200B;을 구성합니다.

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="SMS API 자격 증명 및 채널 표면 구성" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1765241812951" alt="SMS API 자격 증명 및 채널 표면 구성"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="SMS API 자격 증명 및 채널 표면 구성">SMS API 자격 증명 및 채널 표면 구성</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer를 SMS 서비스 공급자에 연결하는 방법과 SMS 채널 표면을 만드는 방법을 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="사용자 정의 SMS 공급자 구성" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1765241812924" alt="사용자 정의 SMS 공급자 구성"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="사용자 정의 SMS 공급자 구성">사용자 정의 SMS 공급자 구성</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer에서 사용자 지정 SMS 공급자를 구성하고, API 자격 증명 및 웹후크를 설정하고, 옵트인/옵트아웃 키워드를 관리하고, 개인화된 캠페인을 시작하는 방법에 대해 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="MMS API 자격 증명 및 채널 표면 구성" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1765241812943" alt="MMS API 자격 증명 및 채널 표면 구성"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="MMS API 자격 증명 및 채널 표면 구성">MMS API 자격 증명 및 채널 표면 구성</a>
                    </p>
                    <p class="is-size-6">Journey Optimizer를 MMS 서비스 제공자에 연결하는 방법과 MMS 채널 표면을 만드는 방법을 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="Journey Optimizer에서 RCS 설정" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1765241812927" alt="Journey Optimizer에서 RCS 설정"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Journey Optimizer에서 RCS 설정">Journey Optimizer에서 RCS 설정</a>
                    </p>
                    <p class="is-size-6">사용자 정의 SMS 공급자를 사용하여 Adobe Journey Optimizer에서 인터랙티브한 브랜디드 RCS 메시지를 구성하고 전송하는 방법을 알아봅니다. 이 튜토리얼에서는 API 자격 증명, 웹후크, 채널 구성을 설정한 다음, 풍부하고 개인화된 메시지 경험을 제공하는 여정을 빌드하며, 이 모든 과정은 기본 메시지 앱 내에서 이루어집니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## 개인 정보 보호 법률 및 플랫폼 지침을 준수하도록 합니다.

<!-- CARDS
* https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
{image = help/mobile-learning-hub/assets/privacy.webp}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables
{cta = Watch}
{target = _blank}
* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Adobe Journey Optimizer의 개인 정보 기능" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Adobe Journey Optimizer의 개인 정보 기능"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Adobe Journey Optimizer의 개인 정보 기능">Adobe Journey Optimizer의 개인 정보 보호 기능</a>
                    </p>
                    <p class="is-size-6">개인 정보 보호 요청 처리, 사용자 작업 감사, 동의 관리, 거버넌스 규칙 적용 및 고객 관리 키와 같은 고급 보안 옵션 활용 방법을 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">자세히 알아보기</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="데이터 거버넌스 프레임워크 개요" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1765241813815" alt="데이터 거버넌스 프레임워크 개요"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" title="데이터 거버넌스 프레임워크 개요">데이터 거버넌스 프레임워크 개요</a>
                    </p>
                    <p class="is-size-6">Adobe Experience Platform의 거버넌스 기능을 이해합니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="레이블을 사용한 데이터 분류" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1765241813814" alt="레이블을 사용한 데이터 분류"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="레이블을 사용한 데이터 분류">레이블을 사용하여 데이터 분류</a>
                    </p>
                    <p class="is-size-6">스키마 및 데이터 세트에 레이블을 적용하는 방법에 대해 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="데이터 사용 정책 만들기" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1765241813810" alt="데이터 사용 정책 만들기"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="데이터 사용 정책 만들기">데이터 사용 정책 만들기</a>
                    </p>
                    <p class="is-size-6">데이터 사용 정책을 만들고 관리하는 방법을 알아봅니다.</p>
                </div>
                <a href="https://experienceleague.adobe.com/ko/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">시청</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->


## 일반적인 구현 위험 및 이를 피하는 방법

대부분의 모바일 문제는 Journey Optimizer 여정 또는 캠페인 자체가 아니라 **SDK 또는 데이터 수집 구성**&#x200B;에서 발생합니다. 아래 표를 사용하여 무엇이 잘못되었는지 식별한 다음, 자세한 내용을 보려면 해당 섹션을 확장하십시오.

### 함정 개요

| # | 문제/증상 | 일반적인 위험 | 요약 정보 |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | 가이드 채널 설정에 실패하여 트래픽이 없거나 적음 | [SDK 버전 또는 확장이 정렬되지 않음](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | SDK/확장 버전 업데이트, Assurance에서 유효성 검사 |
| 2 | 배치 추적 실패, AEP 오류 | [데이터 스트림 또는 데이터 세트가 잘못 구성됨](#2-misconfigured-datastreams-or-datasets) | 이벤트 데이터 세트에 이벤트 매핑 및 프로필 데이터 세트에 프로필 매핑 |
| 3 | 여정이 실행되지 않음, 홀수 개인화 | [ID 또는 동의 누락/불일치](#3-missing-or-inconsistent-identity-and-consent) | Edge ID 및 동의 구현, Assurance에서 확인 |
| 4 | 푸시 게재나 보고서 열기 없음 | [푸시 토큰 등록 또는 추적 끊김](#4-push-token-registration-and-tracking-not-wired-correctly) | SDK을 통해 토큰 등록 및 상호 작용 추적 수정 |
| 5 | 활성 캠페인에도 불구하고 인앱 노출 횟수 없음 | [인앱 메시지 또는 콘텐츠 카드가 표시되지 않음](#5-in-app-messages-or-content-cards-not-displaying) | 메시징 확장, 트리거 및 Assurance 의사 결정 응답 확인 |

### 위험당 세부 지침

증상과 일치하는 함정을 열어 확인해야 할 사항과 이를 수정하는 방법을 확인합니다.

+++ &#x200B;1. SDK 버전 및 확장이 채널 요구 사항과 일치하지 않음
**확인할 내용**

- 푸시 또는 인앱 활동이 디바이스에 도달하지 않습니다.
- 안내식 채널 설정 또는 채널 유효성 검사에 실패했습니다.
- Assurance에 누락된 Journey Optimizer, Edge 또는 ID 확장이 표시됩니다.

**확인할 내용**

- 안내 채널 설정에 필요한 최소 **Mobile Core** 및 **Journey Optimizer** 확장 버전을 사용 중입니까?
- **Assurance**&#x200B;의 확장 및 이벤트 아래에서 다음을 수행합니다.
   - 예상 확장이 로드되었습니까?
   - 이벤트가 Edge Network으로 전송되고 승인됩니까?

**해결 방법**

- 지원되는 모바일 SDK 및 Journey Optimizer 확장 버전으로 업그레이드하십시오.
- 앱을 다시 빌드하고 Assurance에 다시 연결한 다음 안내가 있는 채널 설정을 다시 실행합니다.

참조: [모바일 및 웹 설정](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config){target="_blank"}

+++

+++ &#x200B;2. 잘못 구성된 데이터스트림 또는 데이터세트
**확인할 내용**

- Platform 데이터 세트에서 이벤트 또는 푸시 추적 배치가 실패합니다.
- 데이터 수집 오류(예: &quot;업데이트는 이벤트에 대해 지원되지 않음&quot;).
- 푸시 또는 인앱 보고서에 추적이 거의 또는 전혀 표시되지 않습니다.

**확인할 내용**

- Journey Optimizer 추적에 대해 만든 **시스템 스키마 또는 데이터 세트**&#x200B;를 변경한 사람이 있습니까?
- **데이터스트림**&#x200B;에서:
   - 경험 이벤트가 **이벤트 데이터 세트**&#x200B;에 매핑됩니까?
   - 프로필 특성이 **프로필 데이터 세트**&#x200B;에 매핑됩니까?

**해결 방법**

- AJO에서 만든 시스템 데이터 세트/스키마를 편집하지 마십시오.
- 데이터스트림 매핑(이벤트 → 이벤트 데이터 세트, 프로필 → 프로필 데이터 세트)을 수정합니다.
- 임시 변경 사항 대신 가이드 채널 설정 또는 문서화된 데이터 스트림 단계를 선호합니다.

참조: [Adobe Journey Optimizer의 푸시 알림 흐름](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ &#x200B;3. 신원 및 동의의 누락 또는 불일치
**확인할 내용**

- 여정이 앱 사용자의 예상대로 트리거되지 않습니다.
- Personalization이 다른 채널의 사용자 동작과 일치하지 않습니다.
- 이벤트는 Experience Platform에 표시되지만 프로필은 단편적으로 보입니다.

**확인할 내용**

- **Edge Network용 ID**&#x200B;를 구현하고 안정적인 기본 ID(예: 로그인 ID)를 전송합니까?
- 환경 설정이 변경될 때 **Edge Network에 대한 동의**&#x200B;가 구현되고 업데이트됩니까?
- **Assurance**&#x200B;에서:
   - 아웃바운드 이벤트에는 동의 값이 포함됩니까?
   - 여기에 ECID와 기본 ID가 일관되게 포함됩니까?

**해결 방법**

- 앱에서 **Edge Network에 대한 ID**&#x200B;을(를) 구현하거나 수정합니다.
- **Edge Network에 대한 동의**&#x200B;를 구현하고 앱의 동의 UI에 연결합니다.
- 모든 관련 이벤트에 ID 및 동의가 나타날 때까지 Assurance에서 다시 테스트합니다.

[Platform Mobile SDK 구현에 대한 동의 구현](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/app-implementation/consent){target="_blank"}을 참조하세요.

+++

+++ &#x200B;4. 푸시 토큰 등록 및 추적이 올바르게 배선되지 않음
**확인할 내용**

- 캠페인이나 여정이 실행되더라도 사용자는 푸시 알림을 받지 못합니다.
- 푸시 보고서에는 열람, 취소 또는 상호 작용이 표시되지 않습니다.

**확인할 내용**

- 앱이 Journey Optimizer 확장에 푸시 토큰을 등록합니까?
   - 처음 설치 시?
   - 각 앱 업데이트 후?
   - OS가 토큰을 새로 고칠 때마다?
- 사용자가 알림을 열거나 취소하면 Assurance에서 이벤트 추적이 표시됩니까?

**해결 방법**

- 다음 코드를 추가하거나 수정합니다.
   - 토큰을 만들거나 새로 고칠 때마다 Journey Optimizer 모바일 확장을 통해 토큰을 등록합니다.
   - Mobile SDK을 통해 푸시 상호 작용 이벤트(열기, 닫기, 사용자 지정 작업)를 보냅니다.
- Assurance을 사용하여 등록 및 추적 이벤트가 예상대로 실행되는지 확인합니다.

참조: [Adobe Journey Optimizer의 푸시 알림 흐름](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ &#x200B;5. 인앱 메시지 또는 콘텐츠 카드가 표시되지 않음
**확인할 내용**

- 활성 캠페인이나 여정이 있더라도 인앱 메시지 또는 콘텐츠 카드는 표시되지 않습니다.
- 보고에 0개의 노출이 표시됩니다.

**확인할 내용**

- **Journey Optimizer 모바일 메시징/인앱 확장 기능** 및 **메시징 SDK**&#x200B;이(가) 앱에 설치 및 등록되어 있습니까?
- **태그** 구성에서:
   - 올바른 이벤트(예: 화면 보기 또는 사용자 지정 이벤트)에 대한 요청을 트리거하는 규칙이 있습니까?
- **Assurance**&#x200B;에서:
   - 이러한 이벤트가 발생하면 인앱 또는 콘텐츠 카드 결정 요청이 표시됩니까?
   - Edge Network에서 응답이 돌아온 것을 보시나요?

**해결 방법**

- 필요한 메시징 확장을 설치하고 등록합니다.
- 대상 이벤트(화면, 사용자 지정 이벤트)에 대한 결정을 트리거하는 규칙을 추가하거나 수정합니다.
- 콘텐츠 카드의 경우 다음을 확인하십시오.
   - 메시징 SDK API를 통해 카드를 가져옵니다.
   - UI에서 렌더링합니다.
   - SDK을 통해 상호 작용을 다시 추적합니다.

다음을 참조하십시오.
- [인앱 메시지 만들기 및 보내기](https://experienceleague.adobe.com/en/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp){target="_blank"}
- [모바일 SDK에서 콘텐츠 카드 지원 구성](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp){target="_blank"}

+++

## 추가 리소스

- [더 빠른 개인화(블로그)를 위해 모바일에서 CDN 기반 클라이언트측 개인화(ODD) 사용](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626){target="_blank"}
- [다음 수준의 모바일 앱 참여 및 성장에 대한 비밀(Summit 세션)](https://business.adobe.com/summit/2025/sessions/the-secret-to-nextlevel-mobile-app-engagement-s603.html)
