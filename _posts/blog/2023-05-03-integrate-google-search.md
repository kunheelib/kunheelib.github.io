---
title: "[GitHub Blog] 블로그 검색 노출하기 - Google Search Console"
excerpt: ""
categories:
  - blog
tags:
  - google analytics
  - google search console
  - jekyll
  - blog
toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: ""

date: 2023-05-03
last_modified_at: 2023-05-06
---
📌 **Google Search Console**을 이용해 검색창을 노출하는데는 **소유권 확인이 필수**입니다.<br>
소유권을 확인하는데에는 **HTML 파일**, **HTML 태그**, **Google Analytics** 등등 여러 방법이 있습니다.<br><br>
본 포스팅에서는 **Google Analytics**를 이용한 방법이 기재되어 있습니다.<br>
**Google Analytics** 설정이 안되어 있는 경우 [**블로그 방문 통계보기 - Google Analytics**](https://kunheelib.github.io/blog/integrate-google-analytics/)에 포스팅을 참고해주세요.
{: .notice--primary}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 준비하기

[**Google Search Console**](https://search.google.com/search-console) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![images](https://user-images.githubusercontent.com/131929869/235844953-d777a25c-970e-489c-9d68-e851bbf3bbdf.png)

![images](https://user-images.githubusercontent.com/131929869/235851821-e0e8b31b-fea5-4d69-9a07-9d4cba20ebf2.png)

>
 1️⃣ **블로그 URL**을 입력
>
 **`계속`**

![images](https://user-images.githubusercontent.com/131929869/235844967-a0b35f53-ddc9-4af3-baef-798d8a5410fc.png)

>
 2️⃣ **Google 애널리틱스** 아코디언 클릭
  : 앞서 말씀드렸지만 본 포스팅에서는 **Google Analytics**을 이용하여 소유권을 확인합니다.
>
 3️⃣ **`확인`**을 눌러 소유권 확인 **검증**을 진행 합니다.

⚠️ **만약 소유권 확인에 실패했다면?**<br><br>
 : **_includes** > **head.html**안에<br>
   **analytics-providers** > **google-gtag.html**에 있는 **`<script>`**가 모두 반영되어 있는지 확인해주세요.<br>
{: .notice--warning}

![images](https://user-images.githubusercontent.com/131929869/235852095-8052da32-962d-4781-8674-840633747dd1.png)

>
 **`완료`**

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 적용하기

## [2.1] sitemap.xml 만들기

<script src="https://gist.github.com/kunheelib/74f60a40cfea9f9719a8df38430097b9.js"></script>

해당 파일을 생성하여 **root( / )**에 만듭니다.
{: .notice}

💡 **sitemap.xml이란?**<br><br>
 : 웹사이트 내 모든 페이지의 목록을 나열한 파일로 책의 목차와 같은 역할을 합니다.<br>
 자세한 내용은 [**sitemap.xml이란?**]() 에서 자세한 설명을 작성하였으니 참고해주세요.
{: .notice--info}

## [2.2] robots.txt 만들기

<script src="https://gist.github.com/kunheelib/2af61e0fd50825ed1c6661b8cdc3adb8.js"></script>

해당 파일을 생성하여 **root( / )**에 만듭니다.
{: .notice}

💡 **robots.txt란?**<br><br>
 : 웹사이트에 대한 검색엔진 로봇들의 접근을 조절해주고 제어해주는 역할, 그리고 로봇들에게 웹사이트의 사이트맵이 어디있는지 알려주는 역할을 합니다.<br>
 자세한 내용은 [**robots.txt란?**]() 에서 자세한 설명을 작성하였으니 참고해주세요.
{: .notice--info}

## [2.3] sitemap 적용

[**Google Search Console**](https://search.google.com/search-console) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![images](https://user-images.githubusercontent.com/131929869/235844973-37214466-fbc2-49fc-9f90-f699db09e198.png)

>
 좌측 **Sitemaps**를 클릭하여 새 사이트맵을 추가합니다.<br><br>
 작성한 **sitemap.xml**을 내용에 기재한 후 **`제출`**을 클릭합니다.

![images](https://user-images.githubusercontent.com/131929869/235844974-0cc13de9-01f9-4b0b-8110-500f13257cc1.png)

>
 추가된 항목의 상태가 **성공**인지 확인해주세요.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 확인하기

![images](https://user-images.githubusercontent.com/131929869/235868952-83813d80-d03e-4977-b722-e990ea103c0a.png)

>
 2023-05-03<br>
  : 저도 아직 노출이 되지 않습니다. 적용되면 다시 업데이트하겠습니다.
>
 2023-05-04<br>
  : 하루 걸렸네요. 구글에서 검색이 가능합니다.<br>
  포스팅한 글은 아직 보이지 않는데요. 만약 시간이 지나도 보여지지 않는다면 해결 후 추가적으로 업데이트 하겠습니다.<br><br>
  ![image](https://user-images.githubusercontent.com/131929869/236216215-1c68891c-409b-4c5d-9a59-fb77c051c0a3.png)



😧 모든 절차를 완료 했는데 검색을 해도 노출이 되지 않아요!<br><br>
 : **Search Console**에서 사이트 관련 데이터를 수집하여 처리하려면 시간이 필요하기 때문입니다.<br>
  **정상적인 현상**이니 기다려주시면 될 것 같습니다.<br><br>
  추가적으로 Search Console에서 수집한 데이터는 **48시간이 지난 후**에야 Search Console 및 Google Analytics에서 조회가 가능합니다.<br>
{: .notice--success}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.