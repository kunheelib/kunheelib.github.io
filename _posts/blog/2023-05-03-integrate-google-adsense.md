---
title: "[GitHub Blog] 블로그 광고 달기 - Google Adsense"
excerpt: ""
categories:
  - blog
tags:
  - google analytics
  - google adsense
  - jekyll
  - blog
toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: ""

date: 2023-05-03
last_modified_at: 2023-05-06
---
📌 **Google Adsense와 Google Ads의 차이**<br><br>
 : **Google Adsense**는 **게시자**를 위한 프로그램입니다.<br>
 블로그 또는 포럼을 소유하거나 관리하고 있으며 수익을 창출하려고 하는 경우 사용하면 됩니다.<br><br>
 **Google Ads**는 **광고주**를 위한 프로그램입니다.<br>
 비즈니스의 성장과 매출 증대에 중점을 두고 웹사이트 또는 앱에서 제품이나 서비스를 광고하려는 경우 사용하시면 됩니다.<br><br>
 참조 : [**Google Adsense 고객센터**](https://support.google.com/adsense/answer/76231?hl=ko)
{: .notice--primary}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 준비하기

[**Google Adsense**](https://adsense.google.com/) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![image](https://user-images.githubusercontent.com/131929869/235920355-4687aa92-85c5-4100-8da7-4f0a60fcdf93.png)

![image](https://user-images.githubusercontent.com/131929869/235919653-ffa8bc8a-795b-46e2-9632-7fb7d11d7a9c.png)

>
 1️⃣ **블로그 URL**을 입력
>
 **`애드센스 사용 시작`**

![image](https://user-images.githubusercontent.com/131929869/235922450-6f902d69-4df6-405c-ab3a-7d6f1eda5667.png)

![image](https://user-images.githubusercontent.com/131929869/235922889-f2e606db-2179-4e7e-a01a-a7f160019d6c.png)

>
 2️⃣ **계정의 정보를 입력**
 : 개인 정보가 포함 되어있어 건너 뛰겠습니다.
>
 3️⃣ **`탐색` 클릭 후 광고 표시 위치를 설정**
>
 **`사이트에 적용`**

❗광고를 표시하기 위해서는 **자동 광고** 선택이 필수적 입니다.<br><br>
  : 본 포스팅에서는 **광고 위치**를 **기본 설정**을 하겠습니다.<br>
 표시 위치의 변경을 원하시면 우측 아코디언들을 클릭해서 조작할 수 있습니다.
 {: .notice--danger}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 적용하기

![image](https://user-images.githubusercontent.com/131929869/235925543-fe2bb53f-3bbc-4553-b091-ffecc6dce6f6.png)

![image](https://user-images.githubusercontent.com/131929869/235927561-b3d14398-8875-4cb3-8f6a-fb5544d6812f.png)

```javascript
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-3229800559788956" crossorigin="anonymous"></script>
 ```

>
 1️⃣ **애드센스 사이트 연결** 

<script src="https://gist.github.com/kunheelib/5ac40b005315558419bb00baccd74295.js"></script>

>
 **_includes** > **head.html**안에 위의 **`<script>`**를 붙여넣습니다.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 확인하기

![image](https://user-images.githubusercontent.com/131929869/235932013-14a89003-59bf-4915-ad8e-569731f3d2fe.png)

>
 2023-05-03<br>
  : 저도 아직 광고가 표시 되지 않습니다. 승인되면 다시 게재하도록 하겠습니다.

😧 언제 심사가 완료되나요?<br><br>
 : 확인은 일반적으로 며칠 이내에 완료되지만, 경우에 따라 2~4주가 소요 될 수 있습니다.<br><br>
 참조 : [**Google Adsense 고객센터**](https://support.google.com/adsense/answer/7402256?sjid=17071070489802319017-AP&visit_id=638187173758244932-1577473137&rd=1)
{: .notice--success}