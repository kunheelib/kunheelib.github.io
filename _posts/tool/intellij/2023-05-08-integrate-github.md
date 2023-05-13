---
title: "[IntelliJ] Git 연동하기 - GitHub"
excerpt: "IntelliJ에서 GitHub 연동하는 방법"
categories:
  - tool
tags:
  - maven
  - spring
  - tomcat
  - git
  - github
  - intellij

toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: ""

date: 2023-05-08
last_modified_at: 2023-05-10
---

<!--
📌 **개발 환경**
 : 
    🔹 **OS** : Windows 11<br>
    🔹 **Java** : jdk1.8.0_351<br>
    🔹 **Git** : 2.40.1.windows.1<br>
    🔹 **Tomcat** : apache-tomcat-9.0.71<br>
    🔹 **IntelliJ IDEA** : 2020.1
{:.notice--primary}
-->

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] GitHub Token 생성

📌 **본 포스팅은 IntelliJ에 GitHub Token을 이용하여 연결을 하게 됩니다.**<br><br>
만약 이미 생성되어 있으신 경우 생략해주시고 [**[2] 연동하기**](#2-연동하기)를 진행해주세요.
{:.notice--primary}

![image](https://user-images.githubusercontent.com/131929869/236964726-4af944c4-1831-4d3c-a906-6a4e9c693dd7.png)

>
 화면 상단의 **계정 아이콘**을 클릭합니다.
>
 **Settings**을 클릭합니다.

![image](https://user-images.githubusercontent.com/131929869/236964871-2f27e202-9c3a-42ba-8ab1-4d2c60e3d44c.png)

>
 **Developer settings**를 클릭합니다.

![image](https://user-images.githubusercontent.com/131929869/236964966-6c7b860f-ae3d-4fd2-a35a-e5eb04c99b40.png)

>
 **Personal access tokens** 아코디언을 클릭합니다.
 >
 **Tokens(classic)**을 클릭합니다.
 >
 **Generate new token**을 클릭합니다.
 >
 **Generate new token(classic)**을 클릭합니다.

![image](https://user-images.githubusercontent.com/131929869/236864466-6f762984-4d64-4a0f-a43a-fe60ab14d74e.png)

>
 토큰에대한 설명을 입력합니다.
 : 선택사항입니다. 필요한 경우 입력해주세요.
>
 토큰의 유효기간을 설정합니다.
 : (본 포스팅에서는 **No expiration**을 선택했습니다.)
>
 필요한 항목들을 선택합니다.
 : (본 포스팅에서는 **모든 항목**을 선택했습니다.)


💡**Scope의 설명**<br><br>
 : GitHub Docs의 내용을 기재해두었습니다.<br><br>
**OAuth 앱에 대한 범위** : <https://docs.github.com/ko/apps/oauth-apps/building-oauth-apps/scopes-for-oauth-apps>
{:.notice--info}

**이름** | **설명**
-----|-----------
`(no scope)` | 공개 정보에 대한 읽기 전용 액세스 권한 부여합니다. (사용자 프로필 정보, 리포지토리 정보 및 gist 포함)
`repo` | 퍼블릭 및 프라이빗 리포지토리에 대한 모든 액세스 권한을 부여합니다.<br>(코드에 대한 읽기 및 쓰기 권한, 커밋 상태, 리포지토리 초대, 협력자, 배포 상태 및 리포지토리 웹후크 포함).<br>참고: 리포지토리 관련 리소스 외에도 `repo` 범위는 프로젝트, 초대, 팀 멤버 자격 및 웹후크를 포함하여 조직 소유 리소스를 관리할 수 있는 액세스 권한을 부여합니다.<br>이 범위는 사용자가 소유한 프로젝트를 관리하는 기능도 부여합니다.
`repo:status` | 퍼블릭 및 프라이빗 리포지토리의 커밋 상태에 대한 읽기/쓰기 액세스 권한을 부여합니다.<br>이 범위는 코드에 대한 액세스 권한을 부여하지 않고 다른 사용자 또는 서비스에 프라이빗 리포지토리 커밋 상태에 대한 액세스 권한을 부여하는 데만 필요합니다. 
`repo_deployment` | 퍼블릭 및 프라이빗 리포지토리의 배포 상태에 대한 액세스 권한을 부여합니다.<br>이 범위는 코드에 대한 액세스 권한을 부여하지 않고 다른 사용자 또는 서비스에 배포 상태에 대한 액세스 권한을 부여하는 데만 필요합니다. 
`public_repo` | 퍼블릭 리포지토리에 대한 액세스를 제한합니다.<br>여기에는 퍼블릭 리포지토리 및 조직의 코드, 커밋 상태, 리포지토리 프로젝트, 협력자 및 배포 상태에 대한 읽기/쓰기 액세스가 포함됩니다.<br>공용 리포지토리를 별표로 지정하는 데도 필요합니다.
`repo:invite` | 리포지토리에서 협업하도록 초대에 대한 수락/거절 기능을 부여합니다.<br>이 범위는 코드에 대한 액세스 권한을 부여하지 않고 다른 사용자 또는 서비스에 초대에 대한 액세스 권한을 부여하는 데만 필요합니다. 
`security_events` | code scanning API의 보안 이벤트에 대한 읽기 및 쓰기 액세스를 부여합니다.<br>이 범위는 코드에 대한 액세스 권한을 부여하지 않고 다른 사용자 또는 서비스에 보안 이벤트에 대한 액세스 권한을 부여하는 데만 필요합니다.
`admin:repo_hook` | 퍼블릭 또는 프라이빗 리포지토리의 리포지토리 후크에 대한 읽기, 쓰기, ping 및 삭제 액세스 권한을 부여합니다.<br>`repo` 와 `public_repo` 범위는 리포지토리 후크를 포함하여 리포지토리에 대한 모든 권한을 부여합니다.<br> `admin:repo_hook` 범위를 사용하여 리포지토리 후크로 액세스를 제한합니다. 
`write:repo_hook` | 퍼블릭 또는 프라이빗 리포지토리의 후크에 대한 읽기, 쓰기 및 ping 액세스 권한을 부여합니다.
`read:repo_hook` | 퍼블릭 또는 프라이빗 리포지토리의 후크에 대한 읽기 및 ping 액세스 권한을 부여합니다.
`admin:org` | 조직 및 해당 팀, 프로젝트, 멤버 자격을 완전히 관리합니다.
`write:org` | 조직 멤버 자격, 조직 프로젝트 및 팀 멤버 자격에 대한 읽기 및 쓰기 권한입니다. 
`read:org` | 조직 멤버 자격, 조직 프로젝트 및 팀 멤버 자격에 대한 읽기 전용 권한입니다. 
`admin:public_key` | 공개 키를 완전히 관리합니다.
`write:public_key` | 공개 키에 대한 세부 정보를 만들고 나열하고 봅니다.
`read:public_key` | 공개 키에 대한 세부 정보를 나열하고 봅니다.
`admin:org_hook` | 조직 후크에 대한 읽기, 쓰기, ping 및 삭제 액세스 권한을 부여합니다.<br>참고: OAuth 토큰은 OAuth 앱에서 만든 조직 후크에서만 해당 작업을 수행할 수 있습니다.<br>Personal access tokens는 사용자가 만든 organization 후크에서만 이러한 작업을 수행할 수 있습니다.
`gist` | gist에 대한 쓰기 권한을 부여합니다.
`notifications` | 다음 권한을 부여합니다.<br>- 사용자의 알림에 대한 읽기 권한<br>- 스레드에 대한 읽기 권한으로 표시<br>- 리포지토리에 대한 조사식 및 비조사식 액세스 권한,스레드 구독에 대한 읽기, 쓰기 및 삭제 액세스 권한
`user` | 프로필 정보에 대한 읽기/쓰기 권한만 부여합니다.<br>이 범위에는 `user:email`과 `user:follow`가 포함됩니다.
`read:user` | 사용자 프로필 데이터를 읽을 수 있는 액세스 권한을 부여합니다.
`user:email` | 사용자의 이메일 주소에 대한 읽기 권한을 부여합니다.
`user:follow` | 다른 사용자에 대한 팔로우 및 팔로우 취소 관련 액세스 권한을 부여합니다.
`project` | 사용자와 조직 projects에 대한 읽기/쓰기 액세스 권한을 부여합니다.
`read:project` | 사용자 및 조직 projects에 대한 읽기 전용 액세스 권한을 부여합니다.
`delete_repo` | 관리 가능한 리포지토리 삭제에 대한 액세스 권한을 부여합니다.
`write:discussion` | 팀 토론에 대한 읽기 및 쓰기 권한을 허용합니다.
`read:discussion` | 팀 토론에 대한 읽기 권한을 허용합니다.
`write:packages` | GitHub Packages에서 패키지를 업로드하거나 게시할 수 있는 액세스 권한을 부여합니다.
`read:packages` | GitHub Packages에서 패키지를 다운로드하거나 설치할 수 있는 액세스 권한을 부여합니다.
`delete:packages` | GitHub Packages에서 패키지를 삭제할 수 있는 액세스 권한을 부여합니다.
`admin:gpg_key` | GPG 키를 완전히 관리합니다.
`write:gpg_key` | GPG 키에 대한 세부 정보를 만들고 나열하고 봅니다.
`read:gpg_key` | GPG 키에 대한 세부 정보를 나열하고 봅니다.
`codespace` | codespace를 만들고 관리하는 기능을 부여합니다.<br>codespace는 다른 범위 집합이 있을 수 있는 GITHUB_TOKEN을 노출할 수 있습니다.
`workflow` | GitHub Actions 워크플로 파일을 추가하고 업데이트하는 기능을 부여합니다.<br>경로와 내용이 모두 동일한 파일이 동일한 리포지토리의 다른 분기에 있는 경우 이 범위 없이 워크플로 파일을 커밋할 수 있습니다.<br>워크플로 파일은 다른 범위 집합을 포함할 수 있는 GITHUB_TOKEN을 노출할 수 있습니다.
{:.notice}

![image](https://user-images.githubusercontent.com/131929869/236864468-34987488-a346-4610-8486-b24632bacd88.png)

>
 **생성된 토큰을 확인합니다.**

❗**토큰을 생성하고 주의해주세요.**<br><br>
**생성된 토큰은 중요한 권한을 가지고 있습니다.**<br>
유출시 다른 사용자가 해당 계정에 대한 권한을 갖을 수 있으니 **<u>공유하지말고 보안에 주의</u>**해야합니다.
{:.notice--danger}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [2] 연동하기

## [2.1] GitHub 계정 연결

![image](https://user-images.githubusercontent.com/131929869/236864470-a4269f01-703a-4e53-8cdd-790bee4e985a.png)

>
 **`Ctrl` + `Alt` + `S`** 동시에 눌러 **Setting** 창를 열고 **Version Control > Git**를 클릭해주세요.
>
  **Path to Git executable** 우측의 **Test**를 클릭하여 Git의 설치 유무와 버전 정보를 확인합니다.
   : 생략해도 무방합니다.

![image](https://user-images.githubusercontent.com/131929869/236864472-19a7f5b6-733f-49fe-a9b6-052b0f28732b.png)

>
 **Setting** 창를 좌측의 **Version Control > GitHub**를 클릭해주세요.
>
 화면 가운데에 있는 **Add account**를 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236864476-771b54e9-c45a-41a0-8c6e-ae2947eefa9d.png)

>
 열린 팝업창 상단의 **Use Token**을 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236864478-2082f040-11b1-4035-8ce6-e953b20ab0bb.png)

>
 변경된 입력창에 이전 단계에서 **생성한 토큰**을 입력해주세요.

![image](https://user-images.githubusercontent.com/131929869/236864479-9cc513f3-6c11-46a0-8923-e75ff21c0dfc.png)

>
 **계정의 저장소들이 보여지며 연결이 된 것을 확인할 수 있습니다.**

## [2.2] GitHub Repository 연결

![image](https://user-images.githubusercontent.com/131929869/236864481-2e55254f-1c02-4aa0-9d27-891174afba5b.png)

>
 **VCS > Enable Version Control Intergration...**을 클릭합니다.
  : git init과 동일한 동작을 하며, 저장소가 초기화 된다.<br>
  이미 초기화 된경우 메뉴가 보이지 않을 수 있습니다.

![image](https://user-images.githubusercontent.com/131929869/236864483-fc258bec-6acd-4715-bcc0-de90248e3b5e.png)

>
 **Git**을 선택합니다.

![image](https://user-images.githubusercontent.com/131929869/236864486-89cc889c-3a46-4fe9-8787-2c480331cca6.png)

>
 **VCS > Git > Remotes..**을 클릭합니다.
  : 이전 단계에서 Git을 선택해야 해당 서브 메뉴가 생성됩니다.

 ⚠️똑같이 진행해도 안보이는데요?<br><br>
  : **다음과 같은 경우가 있을 수 있습니다.**<br><br>
    1. IntelliJ 2020.1 버전 이상의 경우 VCM 메뉴가 Git으로 변경되었습니다. 보여지는 단어가 조금 다를 수 있으나 동일한 동작을 수행할 수 있습니다.
    2. 프로젝트가  Git에 연결되어 있는지 확인해주세요.(Version Control이 연결되어 있지 않다면 안보일 수 있습니다.)
    3. IntelliJ 버전이 너무 오래되어 지원하지 않을 수 있습니다. 버전을 확인해주시고, 대체할 수 있는 플러그인을 찾아주세요.
{:.notice--warning}

![image](https://user-images.githubusercontent.com/131929869/236864487-57e6e1e0-cba6-4d53-b572-5a629bc7d08e.png)

>
 팝업창이 열리면 연결할 **Repository URL**을 입력합니다.

![image](https://user-images.githubusercontent.com/131929869/236864491-9b712a90-4cd2-46c2-abd6-17b73ea5d587.png)

>
 **추가된 것을 확인할 수 있습니다.**

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [3] 플러그인 설정 - ignore 

💡**ignore이란?**<br><br>
Git에 사용되는 파일중 하나로 <u>특정 파일이나 디렉터리를 제외시켜주는 역할을 합니다.</u><br>
보안적으로 중요한 요소나 불필요한 같은 것들을 정의합니다.
{:.notice--info}

![image](https://user-images.githubusercontent.com/131929869/236864495-3d85fc88-e734-4359-b877-aacda0752c29.png)

>
 **`Ctrl` + `Alt` + `S`** 동시에 눌러 **Setting** 창를 열고 **Plugins**를 클릭해주세요.
>
 검색창에 **ignore**을 검색하여 설치해주세요.

![image](https://user-images.githubusercontent.com/131929869/236864496-5400723d-7cac-430d-9f79-a0d105fa22b0.png)

>
 프로젝트를 **마우스 우클릭 > New > .ignore file > .gitignore file (Git)** 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236864499-6d1fe42a-1fb2-4fda-87bb-088673c95e6b.png)

>
 팝업창이 열리면 **Example user templeate**을 선택해주세요.
  : IntelliJ의 기본 템플릿이 정의됩니다.<br>
  그 외에도 여러가지를 선택할 수 있는데 사용 유형에 맞춰 선택해주세요.

![image](https://user-images.githubusercontent.com/131929869/236864501-2e34f862-2d0e-4e42-ba14-7f90e441b37a.png)

>
 **Add**를 클릭합니다.
  : Git에 연결 후 동작하는것으로 새로운 파일을 Git에 추가하겠는지 물어보는 팝업입니다.

![image](https://user-images.githubusercontent.com/131929869/236864504-d30e4a9c-129e-42e4-bc08-22fcd6a5808f.png)

>
 **좌측 디렉터리에서 추가된 .gitignore을 확인할 수 있습니다.**

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [4] 확인하기

![image](https://user-images.githubusercontent.com/131929869/236996412-e9f22686-f5b0-4e07-adae-ed604b11b2fc.png)

>
 프로젝트를 **마우스 우클릭 > Open in Terminal** 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236996414-c5fa536f-d0f1-4dfd-a712-4e1e03f436de.png)

>
 **하단에 터미널 창이 열리게 되면 업로드를 진행합니다.**

![image](https://user-images.githubusercontent.com/131929869/236996419-7a9aed84-2a32-415c-8922-0222a7df28ff.png)

>
 **업로드 완료된 내용을 확인합니다.**

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
이상 포스팅을 마치겠습니다.