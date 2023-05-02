---
layout:
title: "[GitHub Blog] 블로그 댓글 기능 추가하기"
categories:
  - blog
tags:
  - utterances
  - jekyll
  - blog
toc: true
toc_sticky: true
toc_label: "GITHUB BLOG 댓글"
toc_icon: "blog"
---

# [1] 준비하기

[**utterances**](https://github.com/apps/utterances) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![images](https://user-images.githubusercontent.com/131929869/235621675-4e3c95a4-4166-4e11-ad63-ce1d7907531d.png)
>
 1️⃣ **Install** 버튼 클릭<br>
 : 만약 이미 설치되어 있는 경우 **Configure**가 표시

![images](https://user-images.githubusercontent.com/131929869/235621684-e7563b69-0d72-414c-84a1-1122a51f4727.png)

**댓글을 이슈로 관리할 저장소를 선택하여 설치합니다.**
{: .notice}
>
 2️⃣ **Only select repositories** 선택<br>
 3️⃣ **Combo:Select repositories** 선택 후, **repository** 선택<br>
 4️⃣ **Install** 버튼 클릭

![images](https://user-images.githubusercontent.com/131929869/235621685-c97effe4-fc44-4897-bd4f-5983d115fe5f.png)

**저장소를 설정합니다.**
{: .notice}
>
 5️⃣ **repo**에 **repository** 입력<br>

![images](https://user-images.githubusercontent.com/131929869/235621686-4e7306b6-7bc4-4b88-98f6-64e543488e09.png)

**블로그 포스트와 이슈 매핑 방법에 대한 설정합니다.**
{: .notice}
>
 6️⃣ **Issue title contains page pathname** 선택<br>
 : 본 포스팅에서는 **블로그 글 경로를 이슈의 제목**으로 설정했습니다.

![images](https://user-images.githubusercontent.com/131929869/235621688-32d0e627-992d-4e5a-b601-df6918bd6f1a.png)

**이슈 라벨과 테마를 설정합니다.**
{: .notice}
>
 7️⃣ 본인이 원하는 내용을 입력 및 선택
 : 본 포스팅에서는 **default**값으로 설정했습니다.

![images](https://user-images.githubusercontent.com/131929869/235621693-e2744837-ec6a-4894-b6af-1a9786dedd51.png)

**설정한 값을 토대로 script가 생성됩니다.**
{: .notice}
>
 8️⃣ **Copy** 버튼을 눌러 복사

# [2] 적용하기
![images](https://user-images.githubusercontent.com/131929869/235674433-d89c0ea4-2726-4b0d-8c70-f66675d863d9.png)
>
 1️⃣ **_config.ymd** 파일을 찾습니다.

![images](https://user-images.githubusercontent.com/131929869/235674439-c4a8bb59-ee71-44f7-9416-a3f24982e1c5.png)

**utterances 설정을 적용합니다.**
{: .notice}

>
 2️⃣ **provier** 를 **utterances** 로 변경합니다.<br>
 3️⃣ **utterances**의 **theme**,**issue_term** 을 변경합니다.
 

![images](https://user-images.githubusercontent.com/131929869/235672719-d40160c6-5c4d-4507-b29f-0f6999ea43ee.png)

**댓글을 노출 화면에 적용합니다.**
{: .notice}
>
 1️⃣ 본 포스팅에는 포스팅 화면에만 노출 시킬 것이기에 **_layouts > post.html** 파일을 찾습니다.

![images](https://user-images.githubusercontent.com/131929869/235672731-b7f6bdd3-3cbb-4a98-b866-3aee2e2744e9.png)
>
 2️⃣ 복사된 **script**를 원하는 위치에 붙여넣습니다.

# [3] 확인하기
 
 ![images](https://user-images.githubusercontent.com/131929869/235678003-b822e5d8-98b2-42a7-b66a-0f82ecc22582.png)

이상 블로그 댓글 기능 추가를 마치겠습니다.