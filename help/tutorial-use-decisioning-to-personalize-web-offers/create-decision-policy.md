---
title: 의사 결정 정책 만들기
description: 의사 결정 정책을 사용하여 개인화 중에 사용자에게 게재되는 오퍼를 결정하는 논리를 정의합니다.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
source-git-commit: 9a35160921988103182815efd3551151c09b9bb4
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# 의사 결정 정책 만들기

의사 결정 정책은 대상자에 따라 제공할 최상의 콘텐츠를 선택하기 위해 [!UICONTROL Decisioning] 엔진을 활용하는 오퍼에 대한 컨테이너입니다.

1. 개인화 편집기에서 왼쪽 탐색에서 **[!UICONTROL 결정 정책]** 항목을 클릭한 다음 **[!UICONTROL 결정 정책 추가]**&#x200B;를 클릭합니다.

   ![의사 결정 정책 만들기](assets/decision-policy.png)

1. 선택 전략을 선택하려면 **[!UICONTROL 추가]**&#x200B;를 클릭하십시오.

   ![결정 정책](assets/decision-policy2.png)

1. 대체 오퍼를 선택하려면 **[!UICONTROL 대체 항목 선택]**&#x200B;을 클릭하세요.
1. 결정 정책을 검토하려면 **[!UICONTROL 다음]**&#x200B;을 클릭하세요.
1. 결정 정책을 만드는 프로세스를 완료하려면 **[!UICONTROL 만들기]**&#x200B;를 클릭하십시오.

## 코드 편집기에서 의사 결정 정책 사용

1. 개인화 편집기에서 **[!UICONTROL 정책 삽입]**&#x200B;을 클릭합니다.

   결정 정책에 해당하는 코드가 추가됩니다.

   이 단계에서는 필요한 의사 결정 속성을 코드 내에 직접 포함할 수 있습니다. 이러한 속성은 오퍼 카탈로그에서 사용하는 스키마에 정의되어 있습니다. 표준 특성은 `__experience` 네임스페이스 아래에 구성되는 반면, 조직에 관련된 모든 사용자 지정 특성은 `_<imsOrg>` 네임스페이스 아래에 저장됩니다.

   ![using_decision_policy](assets/Insert-policy.png)

   이 코드는 사용자에 대해 선택된 개인화된 오퍼 목록을 통과하고 웹 페이지에 있는 각 오퍼에 대한 텍스트를 표시합니다. 단락 안에 있는 각 오퍼의 메시지(`offerText`)를 표시하므로 사용자가 맞춤화된 콘텐츠를 명확하게 볼 수 있습니다.

   사용할 수 있는 개인화된 오퍼가 없는 경우 공백이 남지 않도록 대체 오퍼가 표시됩니다.

1. **[!UICONTROL 저장]**&#x200B;을 클릭한 다음 캠페인을 활성화합니다.
