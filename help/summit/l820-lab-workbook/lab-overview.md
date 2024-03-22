---
title: 랩 워크북 - L820 - Adobe Journey Optimizer으로 개인화된 모바일 모먼트 구축
description: 다양한 모바일 시나리오를 살펴보고 Journey Optimizer을 사용하여 웹 및 모바일에 대한 개인화된 경험을 구현하는 방법을 알아봅니다.
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14977
thumbnail: KT-14977.jpeg
source-git-commit: d53c2218ee69c81881b12dedc435826034a710e3
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---


# 랩 워크북

![Adobe Summit - 대체 텍스트](/help/summit/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

>[!IMPORTANT]
>
>SNS에 세션 중 사진이나 스크린샷을 게시하는 것을 삼가 주시기 바랍니다.
>
>**Adobe 기밀 유지**
>본 연구실에서 공유한 정보와 제품 공개는 Adobe의 기밀 정보입니다.
>참여자는 개인 또는 단체에 비밀정보를 복제, 사용, 전파 또는 공개할 수 없다.
>제품 공시는 정보용으로만 제공되며 향후 어떤 기능이나 기능도 보장하지 않으며 언제든지 변경될 수 있습니다. 이와 같이 이러한 제품 기능 또는 기능은 Adobe과의 계약에 포함되어 있지 않거나 어떤 방식으로든 귀하에게 약정되지 않습니다.
>
>**면책조항**
>Adobe은 생성 AI 기술을 활용하는 기능에 대한 조기 액세스를 제공합니다. 이러한 기능은 아직 개발 중이며 예기치 않거나 정확하지 않은 응답을 생성할 수 있습니다. 이 기능을 시장에 출시할 때 귀하의 피드백을 환영합니다.

## L820 - Adobe Journey Optimizer으로 개인화된 모바일 순간 구축

이 실습형 랩에서는 다양한 모바일 시나리오를 살펴보고 Journey Optimizer을 사용하여 웹 및 모바일에 대한 개인화된 경험을 구현하는 방법을 알아봅니다.

### 핵심 사항

* 지원되는 다양한 모바일 경험을 이해합니다.
* 푸시 캠페인을 구성합니다.
* 모바일 인앱 캠페인을 구성하는 방법에 대해 알아봅니다.
* 웹 인앱 메시지를 설정합니다.
* 개인화된 시나리오를 테스트합니다.

### 전제 조건

* 귀하의 좌석 번호를 알고 : 당신은 실험실 기계의 책상 위에서 귀하의 좌석 번호를 찾을 수 있습니다:

![시트 번호](/help/summit/l820-lab-workbook/assets/locate-seat-number.png)
다음에 대한 액세스 권한이 필요합니다.

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}  - 로그인 세부 정보는 연습 중에 제공됩니다.
* [Fréscopa 웹사이트](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### 사용 사례 이해

역동적이고 혁신적인 회사인 Fréscopa는 웹사이트와 모바일 앱에서 제공되는 커피 구독 서비스와 다양한 커피 관련 제품의 독특한 혼합을 통해 커피 경험의 혁신을 전문으로 합니다. 뛰어난 품질과 풍미를 제공하는 Fréscopa는 편리함과 프리미엄 옵션을 원하는 커피 애호가에게 만족감을 선사합니다.

Fréscopa의 비즈니스의 핵심은 커피 구독 서비스에 있으며, 고객에게 고품질의 원두를 직접 주문하실 수 있도록 선별한 제품을 제공합니다. 이러한 개인화된 접근 방식을 통해 커피 애호가들은 자신의 기호에 맞게 신선하고 즐거운 경험을 즐길 수 있습니다.

구독 서비스를 보완한 프레스코파의 웹사이트와 모바일 앱은 커피 관련 상품을 포괄적으로 제공해 고객이 자신의 커피 의식을 탐색하고 강화할 수 있다. 양조 장비부터 장인의 액세서리까지 Fréscopa는 품질과 편리함을 추구하는 커피 애호가를 위한 원스톱 샵을 제공합니다.

Fréscopa는 원활하고 즐거운 고객 여정을 만들기 위해 최선을 다하고 있기 때문에 우수성을 위한 Fréscopa의 노력은 제품을 넘어 확장됩니다. 혁신적인 기술과 고객 중심 접근법의 결합은 Fréscopa를 진화하는 커피 산업의 선두에 자리잡게 합니다. 본질적으로, 프레스코파는 열정과 기술의 융합을 구현하여 개인이 커피를 경험하고 즐기는 방식을 재정의합니다. 품질, 편리함 및 맞춤형 오퍼링에 중점을 둔 Fréscopa는 커피 애호가를 초대해 맛의 여정을 시작하며, 바로 문 앞까지 배달됩니다.



