---
title: "[GitHub Blog] 블로그 검색 노출하기 - Naver Search Advisor"
excerpt: "GitHub 블로그에 네이버 검색 기능 추가하기: Jekyll을 이용한 검색 기능 구현 방법"
categories:
  - blog
tags:
  - naver
  - naver search adavisor
  - jekyll
  - blog
  
toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: "list"

date: 2023-05-04
last_modified_at: 2023-05-09
---

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 준비하기

[**[Naver Search Advisor]**](https://searchadvisor.naver.com/) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![images](https://user-images.githubusercontent.com/131929869/236161346-571a1ad3-3b28-4db7-ba0f-2cb3a96b4dd5.png)

![images](https://user-images.githubusercontent.com/131929869/236161354-f0405d40-56ba-4407-9251-9a011397e844.png)

>
 **블로그 URL**을 입력
>
 입력란 우측에 있는 **화살표** 클릭

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 적용하기

📌 **Naver Search Advisor**을 이용해 검색창을 노출하는데는 **소유권 확인이 필수**입니다.<br>
소유권을 확인하는데에는 Google Search Console과 다르게 **HTML 파일**, **HTML 태그** 두가지 방법만 있습니다.<br><br>
본 포스팅에서는 **HTML 태그**를 이용한 방법이 기재되어 있습니다.<br>
{: .notice--primary}

![images](https://user-images.githubusercontent.com/131929869/236161357-81927872-3045-4e4a-b64c-c89d84ac5937.png)

![images](https://user-images.githubusercontent.com/131929869/236161359-50e9d3c2-15c7-4509-bc27-e0a87c6136f2.png)

>
  **HTML 태그** 선택
  : 앞서 말씀드렸지만 본 포스팅에서는 **HTML 태그**을 이용하여 소유권을 확인합니다.
>
  보여진 **`<meta>`**를 **_includes** > **head.html**안에 반영합니다.
  <script src="https://gist.github.com/kunheelib/5ac40b005315558419bb00baccd74295.js"></script>

## [2.1] sitemap.xml 만들기

**sitemap.xml**를 만드는 방법은 [**[블로그 검색 노출하기 - Google Search Console]**](https://kunheelib.github.io/blog/integrate-google-search/#21-sitemapxml-%EB%A7%8C%EB%93%A4%EA%B8%B0) 에서 다룬적이 있습니다.<br>
생성 방법 및 파일 위치는 동일하니 위 링크를 참고 부탁드리겠습니다.
{: .notice}

## [2.2] robots.txt 만들기

**robots.txt**를 만드는 방법은 [**[블로그 검색 노출하기 - Google Search Console]**](https://kunheelib.github.io/blog/integrate-google-search/#22-robotstxt-%EB%A7%8C%EB%93%A4%EA%B8%B0) 에서 다룬적이 있습니다.<br>
생성 방법 및 파일 위치는 동일하니 위 링크를 참고 부탁드리겠습니다.
{: .notice}

## [2.3] sitemap 적용

![images](https://user-images.githubusercontent.com/131929869/236161361-ffdeee0f-d204-4e30-8ff6-69498091e8ec.png)

>
 좌측에 있는 **요청** > **사이트맵 제출**을 클릭하여 새 사이트맵을 추가합니다.<br>

<!--
## [2.4] robots 검증

![images](https://user-images.githubusercontent.com/131929869/236161364-bec7dfa8-bf78-44ba-bc17-532e907ae7c5.png)

>
 좌측에 있는 **검증** > **robots.txt**을 클릭 후 **`수집요청`**을 클릭합니다.<br>
 : Naver의 경우 Google과 다르게 robots.txt의 
-->
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 확인하기

![image](https://user-images.githubusercontent.com/131929869/236218212-e3334290-ce1e-4270-aaa1-1167cb49af62.png)

>
 2023-05-04<br>
  : 저도 아직 노출이 되지 않습니다. 적용되면 다시 업데이트하겠습니다.
>
 2023-05-06<br>
   : 이건 이틀정도 걸렸네요. 네이버에서도 검색이 가능합니다.<br>
   ![image](https://user-images.githubusercontent.com/131929869/236614462-3dceb0d7-25d4-47aa-8fb6-2f00bada6725.png)

😧 모든 절차를 완료 했는데 검색을 해도 노출이 되지 않아요!<br><br>
 : **Search Advisor**에서 사이트 관련 데이터를 수집하여 처리하려면 시간이 필요하기 때문입니다.( Search Console과 동일 )<br>
  **정상적인 현상**이니 기다려주시면 될 것 같습니다.<br>
{: .notice--success}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.