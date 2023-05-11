---
title: "[GitHub Blog] 블로그 방문 통계 보기 - Google Analytics"
excerpt: "블로그 트래픽 분석하기: Google Analytics를 이용한 방문자 추적 방법"
categories:
  - blog
tags:
  - analytics
  - google
  - google analytics
  - jekyll
  - blog

toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: "list"

date: 2023-05-02
last_modified_at: 2023-05-09
---

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 준비하기

[**[Google Analytics]**](https://analytics.google.com/) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![images](https://user-images.githubusercontent.com/131929869/235710923-c7b8f7ca-87ee-4f5d-8f37-27ce91b97aa5.png)

페이지를 다시 열어 확인할 때는 **관리** > **계정 설정** 에서 확인 및 변경 할 수 있습니다.
 {: .notice}

>
 1️⃣ **계정 이름**을 입력<br>
  : 설정에 직접적으로 영향을 끼치는 부분은 없습니다.

![images](https://user-images.githubusercontent.com/131929869/235710933-2f0d8160-3b65-4462-8463-98b3a199797f.png)

페이지를 다시 열어 확인할 때는 **관리** > **속성 설정** 에서 확인 및 변경 할 수 있습니다.
 {: .notice}

>
 2️⃣ **속성 이름**에 **블로그 URL**을 입력<br>
 3️⃣ **보고 시간대**에 **대한민국** 선택<br>
 4️⃣ **통화**에 **대한민국 원(￦)**<br>
  : 광고를 게재할 경우 수익을 측정하기 위한 단위 입니다.<br>
  광고 설정은 [**GitHub-ads**]() 여기를 참조해주세요!

![images](https://user-images.githubusercontent.com/131929869/235710938-408e63e4-63bc-4d0e-a8cc-70e486d946b8.png)
>
 5️⃣ 본인에게 맞는 정보를 입력합니다.<br>

![images](https://user-images.githubusercontent.com/131929869/235710943-41a50786-814e-4e52-828c-24b89e798510.png)
>
 6️⃣ 본인에게 맞는 정보를 선택합니다.<br>

![images](https://user-images.githubusercontent.com/131929869/235710946-f60f8d7c-2b95-438a-8b79-4b1c92d5b3b0.png)
>
 7️⃣ **대한민국** 선택 후 동의<br>

![images](https://user-images.githubusercontent.com/131929869/235715356-b1365819-dc9a-4fe3-b707-e06bdbaa5b68.png)

최초로 생성했을 때 이미지 처럼 바로 스트림에 대한 **측정ID**를 확인할 수 있습니다.<br>
페이지를 다시 열어 확인할 때는 **관리** > **데이터 스트림** > **항목** 에서 확인 할 수 있습니다.
 {: .notice}

>
 8️⃣ **측정ID** 복사

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 적용하기

![images](https://user-images.githubusercontent.com/131929869/235674433-d89c0ea4-2726-4b0d-8c70-f66675d863d9.png)
>
 1️⃣ **_config.ymd** 파일을 찾습니다.

**analytics 설정을 적용합니다.**
{: .notice}

![images](https://user-images.githubusercontent.com/131929869/235722093-4fa574c2-0c04-4406-8de2-42f0124c95ec.png)

```markdown
<!--Analytics-->
analytics:
  provider               : "google-gtag"
                          # false (default), "google", "google-universal", "google-gtag", "custom"
  google:
    tracking_id          : "G-MVJML397HK"
    anonymize_ip         : # true, false (default)
```

>
 2️⃣ **provier** 를 **google-gtag**로 변경합니다.<br>

 💡 **gtag란?**<br><br>
  : **글로벌 사이트 태그(gtag.js)**는 구글의 사이트 측정, 전환 추적 및 리마케팅 제품을 위한 **웹 태깅 라이브러리**입니다.
 {: .notice--info}
>
 3️⃣ **tracking_id**를 복사한 **측정ID**로 변경합니다.

## Google Analytics 추가 설정

**Google Search Console**의 경우 Analytics를 연계 사용하려면 소유권 확인을 위해 **analytics.js** 또는 **gtag.js** 스니펫을 요구합니다.<br>
추적코드는 페이지의 **`<body>`** 섹션이 아닌 **`<head>`** 섹션 안에 있어야 합니다.<br><br>
**다음 포스팅에서는 Google Search Console를 다루기 때문에 미리 설정하도록 하겠습니다.**<br><br>
참조 : [**[Search Console 고객센터]**](https://support.google.com/webmasters/answer/9008080?sjid=10563790254224309897-AP&visit_id=638187006711769695-421826421&rd=1)
{: .notice}

<script src="https://gist.github.com/kunheelib/5ac40b005315558419bb00baccd74295.js"></script>

>
 **_includes** > **head.html**안에<br>
 **analytics-providers** > **google-gtag.html**에 있는 **`<script>`**를 모두 추가합니다.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 확인하기

![images](https://user-images.githubusercontent.com/131929869/235722718-570933b0-066b-4cc4-8636-0dffbb2dc1ac.png)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.