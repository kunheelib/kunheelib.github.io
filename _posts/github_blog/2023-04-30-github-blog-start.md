---
title: "[GitHub Blog] 블로그 시작하기"
categories:
  - blog
tags:
  - minimal mistakes
  - jekyll
  - blog
toc: true
toc_sticky: true
toc_label: "GitHub Blog  시작"
toc_icon: "blog"
---

# [1] 준비하기

## [1.1] GitHub 가입
[**GitHub**](https://github.com/) 링크에 접속하여 가입을 진행합니다.
{: .notice}

![images](https://user-images.githubusercontent.com/131929869/235370616-b9b806d8-ac02-4c5f-a957-95fa0c82564f.png)

![images](https://user-images.githubusercontent.com/131929869/235370617-d309660d-de94-42a7-8ab4-5b46c035166a.png)

## [1.2] Repository 생성
💡 **Git Repository란?**<br><br>
**Git**으로 관리하는 저장소 입니다.
{: .notice--info}

![images](https://user-images.githubusercontent.com/131929869/235346950-65fa1a34-a4d1-4ba6-a723-562b47960934.png)
>
 1️⃣ 화면 상단의 **+** 를 클릭<br>
 2️⃣ **New repository**를 클릭<br>

![images](https://user-images.githubusercontent.com/131929869/235368047-3fdaa9ef-0101-4803-9b4b-ca2e0ecc0a79.png)
>
 3️⃣ **Repository Name**을 입력합니다.<br>
 4️⃣ **Repository**에 대한 설명을 입력합니다.(선택사항)<br>
 5️⃣ **접근 제어를 설정**합니다. (기본값 : Public)<br>
 6️⃣ **a README file** 선택<br>
 7️⃣ **Create repository** 클릭<br>  

⚠️ **Repository name**<br><br>
  **Pattern : [username].github.io**<br>
  **Repository name**을 위와 같이 작성하게 되면 별도의 작업없이 소스 업로드만으로 호스팅이 되며, 저장소 명이 기본 도메인이 됩니다.<br><br>
  하지만, 이런 이런 간편 호스팅 작업은 계정당 1페이지만 제공합니다.<br>
  만약 정해진 패턴이 아닌 다른 형식의 Repository name을 지정할 경우
  별도로 GitHub Pages 활성화 설정을 해주면 됩니다.<br><br>
  본 포스팅에서는 입문자를 위해 작성하였기 때문에 Pages 설정을 다루지 않겠습니다.<br>
  Pages 설정은 [GitHub-Pages]() 여기를 참조해주세요!
{: .notice--warning}

## [1.3] Git 설치
💡 **Git란?**<br><br>
협업도구, 소스의 버전관리(형상관리) Tool, 무료 소스 관리 시스템입니다.
{: .notice--info}

[**Git**](https://git-scm.com/) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![image](https://user-images.githubusercontent.com/131929869/235352976-82a9c28d-4b6a-4e09-bf3b-53eee709da4a.png)
>
 1️⃣ 사용자 PC 환경에 맞는 **OS**를 선택합니다.<br>

![image](https://user-images.githubusercontent.com/131929869/235353108-26e69335-8b47-48af-a95b-45b7da0d8f7e.png)
>
 2️⃣ 사용자 PC 환경에 맞는 **bit**를 선택합니다.<br>

![image](https://user-images.githubusercontent.com/131929869/235365217-633dd8c9-94ae-4dc8-80cf-565ef2325d5a.png)
>
 3️⃣ 설치가 완료되었다면 **Git Bash.exe** 를 실행합니다.

## [1.4] Git 기본 설정
**Git**이 정상적으로 설치가 되었는지 확인합니다.

```terminal
$ git --version
git version 2.40.1.windows.1
```
**Git**의 환경에 사용자 정보를 지정합니다. 
```terminal
$ git config --global user.name "[user]"
$ git config --global user.email "[user@email.com]"
```

## [1.5] Rudy 설치 및 패키지 설치
[**Ruby for Windos**](https://rubyinstaller.org/downloads/)에 접속하신 후 이미지와 같은 내용을 확인해주세요.
{: .notice}

![images](https://user-images.githubusercontent.com/131929869/235343371-475defc5-6033-4902-868e-727cfb965341.png)


❗**jekyll는 32bit 입니다.**<br><br>
따라서 이미지에서 표시한 것과 동일하게 **32Bit (x86)을 설치**해주셔야 합니다.<br>
만약 64Bit (x64)로 설치시 명령어 등 세팅할 때 오류가 빈번하게 발생합니다.
{: .notice--danger}

**Ruby**가 설치된 버전을 확인합니다.
```terminal
$ ruby -v
ruby 3.2.2 (2023-03-30 revision e51014f9c0) [i386-mingw32]
```


### [1.5.1] jekyll 설치

💡 **jekyll이란?**<br><br>
**Ruby**를 통해 개발된 **정적 웹** 환경을 위한 프레임워크입니다.
{: .notice--info}

💡 **정적 웹이란?**<br><br>
**HTML**,**CSS**,**JavaScript** 등 미리 작성된 콘텐츠 페이지를 서버에 저장해두고,<br>
 클라이언트가 접근하는 시점에 그대로 전달하는 방식의 웹을 말합니다.
{: .notice--info}

**jekyll** 를 설치 합니다.
```terminal
$ gem install jekyll
```
**jekyll** 이 정상적으로 설치가 되었는지 확인합니다.
```terminal
$ gem install jekyll
$ jekyll -v
jekyll 4.3.2
```

### [1.5.2] bundler 설치
💡**bundler이란?**<br><br>
**Ruby** 에서 의존성을 관리하는 도구입니다.<br>
**Gemfile** 이라는 파일에서 의존성을 명시하게되면 **bundler**가 내용을 기반으로 필요한 라이브러리를 설치합니다.
{: .notice--info}

💡**Gem이란?**<br><br>
라이브러리의 개념이며, **Ruby** 의 다양한 **Gem**들을 **Gemfile**에 작성합니다.
{: .notice--info}

**bundler** 를 설치합니다.
```terminal
$ gem install bundler
```
**bundler**가 정상적으로 설치가 되었는지 확인합니다.
```terminal
$ bundle -v
Bundler version 2.4.12
```
**Jekyll**서버를 실행합니다.<br>
**Git**에 파일을 업로드하기 전에 작성한 **markdown(.md)** 내용을 웹상에서 확인할 수 있습니다.

💡 **markdown(.md)란?**<br><br>
일반 텍스트 기반의 경량 마크업 언어입니다.
{: .notice--info}
```terminal
$ bundle exec jekyll serve
```


# [2] 연결하기
## [2.1] Repository 복제
생성된 **GitHub Repository**를 사용자의 로컬 폴더에 복제를 합니다.
```terminal
$ git clone [GitHub Repository URL]
```
## [2.2] Repository 초기화 
현재 위치에서 로컬 저장소를 생성합니다.<br>
명령어를 입력하시면 현재 위치에 **.git** 폴더가 생성됩니다.
```terminal
$ git init
```
## [2.3] Repository 연결
원격 저장소(Git)에 연결합니다.
```terminal
$ git remote add origin [GitHub Repository URL]
```
💡 **branch란?**<br><br>
독립적으로 어떤 작업을 진행하기 위한 개념입니다.<br>
별도 작업을 진행하시지 않았다면 main으로 설정되어있습니다.<br><br>
![image](https://user-images.githubusercontent.com/131929869/235367439-79aaebf9-66f9-4c11-a970-b58eaed155fd.png)
{: .notice--info}

# [3] 테마 적용하기
[**Jekyll 공식 홈페이지**](http://jekyllthemes.org/)<br>
[**minimal-mistakes 공식 홈페이지**](https://mmistakes.github.io/minimal-mistakes/)<br>
[**minimal-mistakes 가이드**](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)<br>
[**minimal-mistakes GitHub**](https://github.com/mmistakes/minimal-mistakes)<br>
{: .notice}

본 포스팅에서는 **jekyll**의 여러 테마중에서 **minimal-mistakes**를 사용합니다.<br>

## [3.1] 테마 내려받기
![image](https://user-images.githubusercontent.com/131929869/235369047-668ad14d-8d7f-4d70-a8de-bc568eb830d1.png)
>
 1️⃣ 위 참조의 GitHub 주소를 접속하신뒤 **<> Code**를 클릭<br>
 2️⃣ **Download ZIP** 클릭

![image](https://user-images.githubusercontent.com/131929869/235370209-6a2da26a-d055-418e-b884-4b1ad0419a88.png)

![image](https://user-images.githubusercontent.com/131929869/235370210-d8605370-f9e7-4ca7-adcb-5b1d20971df6.png)
>
 3️⃣ 필요/불필요 파일 추가 및 삭제

## [3.2] 로컬 서버 확인하기
```terminal
$ bundle exec jekyll serve
```

## [3.3] Git 파일 추가 및 업로드
```terminal
$ git add .
$ git commit m "[message]"
$ git push -u origin [branch]
```
# [4] 확인하기

이상 블로그 시작하기를 마치겠습니다.