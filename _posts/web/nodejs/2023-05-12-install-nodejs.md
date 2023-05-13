---
title: "[Node.js] Node.js 설치하기"
excerpt: "Windows Node.js 설치 가이드"
categories:
  - nodejs
tags:
  - node
  - node.js
  - 18.16.0
  - npm
  - backend

toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: "list"

date: 2023-05-12
last_modified_at: 2023-05-12
---

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 사양 확인하기

📌 프로그램을 설치하기에 앞서 설치할 **컴퓨터의 사양을 확인**해야합니다.
{: .notice--primary}

![image](https://user-images.githubusercontent.com/131929869/236671354-9dfabf44-3c66-4744-9bbc-c49720d25b44.png)

>
 1️⃣ **`Win` + `R`**를 동시에 눌러 **실행** 도구를 엽니다.<br>
 2️⃣ **msinfo32**를 입력하고 **확인**을 클릭합니다.

![image](https://user-images.githubusercontent.com/131929869/236671342-b02745ea-664f-4b9c-bcc0-955ca3500bce.png)

>
 3️⃣ **시스템 정보** 창이 열리면 **OS 이름 및 시스템 종류**의 내용을 확인합니다.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 설치하기

[**[Node.js]**](https://nodejs.org/en/download) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/c5bfa291-76e7-4851-96d6-8b375a73b1e1)

>
 확인한 자신의 사양에 맞게 설치파일을 다운로드 합니다.

😧 이후 특별히 설명이 필요한 내용이 없습니다. 이미지를 참고하여 동일하게 진행해주시면 됩니다.
{: .notice--success}

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/bf35ce15-82b1-4c76-8bf5-98d612b0fb3d)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/780cf4c7-5241-445d-a5a3-442d379659ff)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/c7381016-5dcd-4f3d-80b5-94579207326f)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/2a2d94c3-308e-4b05-9419-01d03902bda3)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/9cc64459-175d-47e2-a343-6c0acd256e1a)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/91f2efb4-4f84-43c2-b2b4-235aaab26c63)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 확인하기

**Node.js**가 정상적으로 설치가 되었는지 확인합니다.

```terminal
$ node -v
v18.16.0

$ npm -v
9.5.1
```

💡**npm이란?**<br><br>
 : Node Package Manager의 약자로, Node.js에 필요한 패키지들을 관리합니다.<br>
  npm 명령어를 사용해 다양한 모듈을 다운로드할 수 있습니다.
{: .notice--info}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.