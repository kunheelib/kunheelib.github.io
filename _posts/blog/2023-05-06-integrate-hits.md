---
title: "[GitHub Blog] 블로그 방문자 수 표시하기"
excerpt: ""
categories:
  - blog
tags:
  - hits
  - minimal mistakes
  - jekyll
  - blog
toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: ""

date: 2023-05-06
last_modified_at: 2023-05-06
---

⚠️ **GitHub에서는 기본적으로 방문자 수를 확인하는 기능을 제공하지 않습니다.**<br><br>
 : 네이버, 티스토리(TISTORY), 벨로그(Velog) 등 타플랫폼은 방문자 수를 제공하면 반면 깃헙 블로그(GitHub Pages)는 제공하지 않습니다.
{: .notice--warning}

❗ **GitHub API를 이용하면 안되나요?**<br><br>
 : GtiHub API를 GitHub Pages의 블로그에 사용하는 것은 **권장하지 않습니다.**<br>
 GitHub Pages의 블로그는 **정적 웹 사이트이기 때문에 서버 측 코드를 실행할 수 없습니다.**<br>
 따라서 API를 요청 및 응답하는 Javascript 코드를 작성해야 해야하는데,<br>
 이 때 API사용을 위한 **Personal Access Token 등의 인증 정보가 노출**될 수 있기 때문에 보안상 주의해야합니다.
{: .notice--danger}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 준비하기

[**Hits**](https://analytics.google.com/) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![image](https://user-images.githubusercontent.com/131929869/236608069-0dcf8ad4-2fcb-4b78-a2a3-456f4a545ab8.png)

>
 **`TARGET URL`**에 블로그 URL을 입력합니다.<br>
 **`OPTION`**에 방문자수를 보여주는 태그를 커스터마이팅 할 수 있습니다.(선택사항)<br>

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 적용하기

![image](https://user-images.githubusercontent.com/131929869/236611595-780d9ac7-ff98-4590-83c9-7b352580bfc0.png)

>
 원하는 형식의 코드를 복사합니다.
  : 저 같은 경우 본 포스팅에 작성할 것이기에 `markdown`을 복사했습니다.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 확인하기

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fkunheelib.github.io&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)

💡**참고해주세요!**<br><br>
 : 이렇게 간단하게 등록할 수 있지만 **Google Analytics** 또는 **GitHub Insights**에서 확인하는 내용과 다를 수 있어요.<br>
 왜냐하면 단순히 **URL 요청에 대한 수치만을 카운트**하기 때문에 그렇습니다.(새로고침만 하셔도 증가하는것을 확인 할 수 있습니다.)
{: .notice--info}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.