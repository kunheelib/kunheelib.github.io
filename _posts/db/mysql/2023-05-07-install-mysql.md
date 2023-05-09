---
title: "[Database] Mysql 설치하기"
excerpt: ""
categories:
  - mysql
tags:
  - mysql
  - 8.0.33

toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: "list"

date: 2023-05-07
last_modified_at: 2023-05-09
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

## 설치 파일 받기

[**[MySQL Community Server]**](https://dev.mysql.com/downloads/mysql/) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

![image](https://user-images.githubusercontent.com/131929869/236672081-f3726856-951c-4fc5-bedf-489b29ab3792.png)

>
 표시되어 있는 항목 **Download** 클릭합니다.

![image](https://user-images.githubusercontent.com/131929869/236672150-c178396a-e017-4956-981e-b808f21352f3.png)

>
 **No thanks, just start my download** 클릭합니다.

## 설치 유형 선택

![image](https://user-images.githubusercontent.com/131929869/236673023-f601b940-1376-4af3-899c-3decb3c0e424.png)

>
 **Developer Default**를 선택합니다.

💡**알고가기**<br><br>
 : **Developer Default**를 선택해서 설치를 할 경우 설명에서 확인할 수 있는 것처럼 여러가지 제품들이 자동으로 설치됩니다.<br>
 설치하는 제품들이 어떤 기능들을 하는지 알아봅시다.<br>
 {: .notice--info}

 |**제품**|**설명**|
 |:---:|:---|
 |**MySQL Server**|MySQL 데이터베이스 서버를 설치합니다. 이를 통해 데이터베이스를 생성하고 관리할 수 있습니다.|
 |**MySQL Shell**|MySQL을 사용하기 위한 고급 셸입니다. 데이터베이스 관리, 쿼리 수행 및 데이터 분석 등을 할 수 있습니다.|
 |**MySQL Router**|MySQL 서버 간의 데이터 전송 및 분산 처리를 관리하는 라우팅 애플리케이션입니다.|
 |**MySQL Workbench**|MySQL 데이터베이스 설계, 개발, 관리를 위한 공식 GUI 도구입니다.|
 |**MySQL Connectors**|MySQL 서버에 연결하기 위한 드라이버를 제공합니다. 여러 가지 프로그래밍 언어로 MySQL 데이터베이스와 연동할 수 있습니다.|
 |**MySQL Documentation**|MySQL에 대한 공식 문서를 설치합니다. MySQL 서버와 관련된 기술 문서, 설치 가이드, 릴리스 노트 등을 포함합니다.|
 {: .notice}

![image](https://user-images.githubusercontent.com/131929869/236673025-e27dea12-6821-4958-8217-937a82db269e.png)

>
 설치에 필요한 것들을 나열해줍니다.<br>
 설치 프로그램이 자동으로 찾아서 시도합니다.<br>
 만약 프로그램에서 **<u>자동으로 해결되지 않는 부분</u>은 필요한 경우 직접 다운로드**받아주시면 됩니다.
 
![image](https://user-images.githubusercontent.com/131929869/236673027-3e9eedce-9d31-46de-b6fa-51e1e68ce5b3.png)

>
 필요한 부분이 아직 충족되지 않았다는 안내창이 열립니다.<br>
 저에게는 필요하지 않는 내용이기에 **Yes** 를 클릭했습니다.<br>
 **<u>꼭 필요한 것일 경우 No를 눌러 관련 자료를 다운로드</u>** 받아주시면 됩니다.

## 설치

![image](https://user-images.githubusercontent.com/131929869/236673028-1c52281d-2a2f-4dac-8bde-44121eb81e4a.png)

>
 설치할 목록을 보여줍니다.<br>
 내용을 확인한 후 **Execute**를 클릭하면 설치가 진행됩니다.**

![image](https://user-images.githubusercontent.com/131929869/236674517-6229fcf9-ed6b-4dcc-bb68-19c93a93e525.png)

![image](https://user-images.githubusercontent.com/131929869/236674744-0fd74ae0-f9f3-42a8-ab61-84f584724723.png)

>
 설치가 완료된 목록을 보여줍니다.<br>
 내용을 확인 후 **Next**를 클릭합니다.

# [3] 세부 설정

## 구성 유형 선택

![image](https://user-images.githubusercontent.com/131929869/236674747-2435764d-e49c-478d-9cd1-e3d0897d14bc.png)

>
 **Config Type**을 **Development Computer** 선택합니다.
  : 본 포스팅에서는 **default**값을 선택합니다.
>
 **TCP/IP**를 `체크`합니다.
  : 본 포스팅에서는 **default**값을 선택합니다.
>
 **Port**는 3306을 설정합니다.
 : 본 포스팅에서는 **default**값을 선택합니다.<br>
 Mysql 기본 포트는 `3306` 입니다.

💡**알고가기**<br><br>
 :![image](https://user-images.githubusercontent.com/131929869/236675166-e25fc5cb-8014-4527-af16-ba0d83ec4f3b.png)
{: .notice--info}

## 인증 방법 선택

![image](https://user-images.githubusercontent.com/131929869/236675141-03e74c81-5244-48a7-9584-8ecc84505c9b.png)

>
 **첫번째 항목**을 선택합니다.

💡**알고가기**<br><br>
 : 🔹**첫번째 항목** : **SHA-256기반의 비밀번호 암호화** 방식이 적용됩니다.<br>
 🔹**두번째 항목** : MySQL 5.7.5버전 이전에 사용되던 Legacy Authentication 방식이 사용되며 **<u>비밀번호가 암호화되지 않은 상태로 저장</u>**되기 때문에, **보안에 취약**합니다.
 {: .notice--info}

## 비밀번호 설정 및 사용자 추가

![image](https://user-images.githubusercontent.com/131929869/236675148-a108fdb3-7f8b-4d43-bc06-1c314c57bb54.png)

> 
 **Root의 패스워드를 입력합니다.**<br>
>
 하단의 경우 필요시 사용 계정을 추가할 수 있습니다.
 : 본 포스팅에서는 추가하지 않겠습니다.

⚠️ **비밀번호를 잊어버리지말고 잘 기억하세요.**<br>
{: .notice--warning}


## 서비스 등록 여부

![image](https://user-images.githubusercontent.com/131929869/236675611-e2ddaedc-fc58-4b00-9bf8-05b8e7cf95d0.png)

>
 기본값으로 선택 후 **Next**를 클릭합니다.<br>

💡**알고가기**<br><br>
 : MySQL의 동작 시점에 대한 설정을 하는 단계입니다.<br><br>
 🔹**가이드대로 진행할 경우**, MySQL이 서비스에 등록되어 부팅시 자동으로 실행됩니다.<br>
 🔹**만약 체크하지 않을 경우**, 서비스가 등록되지 않으며 수동으로 MySQL 서버를 실행시켜야합니다.
 {: .notice--info}

## 서버 파일 권한

![image](https://user-images.githubusercontent.com/131929869/236675631-f9a3b168-03a0-4bb2-b1fb-dae393ce3b50.png)

>
 **첫번째 항목**을 선택 후 **Next**를 클릭합니다.
  : 본 포스팅에서는 **default**값을 선택했습니다.

💡**알고가기**<br><br>
 : MySQL 데이터 디렉터리를 보호하기 위한 단계입니다.<br>
 설치 프로그램이 액세스 권한을 설정하고, 저장된 파일과 폴더의 권한을 업데이트 합니다.<br>
 이렇게 진행하면 디렉터리내에 있는 **<u>데이터와 파일이 무단으로 수정되지 않고 보호</u>**할 수있습니다.<br>
 또한 서버가 잘못 구성되었거나 악성 코드가 실행되는 경우에도 **<u>데이터 유실을 방지</u>**할 수 있습니다.
{: .notice--info}

## 구성 적용

지금까지 위 단계에서 설정했던 내용을 적용시키는 단계입니다.<br>
참고용으로 확인만 하시고 **Next, Execute, Finsh** 를 계속 클릭 해주시면 됩니다.
{: .notice}

![image](https://user-images.githubusercontent.com/131929869/236675681-1fce0ba7-766d-4013-976c-2192a1c858a4.png)

![image](https://user-images.githubusercontent.com/131929869/236675685-8cd79de0-23f3-474a-aae3-972eff4f6e10.png)

![image](https://user-images.githubusercontent.com/131929869/236675687-98f2a015-0eff-45d1-8f61-3e8ed83d3736.png)

![image](https://user-images.githubusercontent.com/131929869/236675689-5ea359e7-f771-4fd1-8039-b54da5684e2a.png)

![image](https://user-images.githubusercontent.com/131929869/236675691-c45208d8-e020-4773-800a-85adf200e03b.png)

>
 [**[비밀번호 설정 및 사용자 추가]**](#비밀번호-설정-및-사용자-추가) 단계에서 설정했단 패스워드를 입력합니다.

![image](https://user-images.githubusercontent.com/131929869/236675692-79bed62f-2ed9-415a-a6fb-5852a69d1213.png)

![image](https://user-images.githubusercontent.com/131929869/236675694-2e6e5de1-3d94-4c67-8efd-f34402538f0b.png)

![image](https://user-images.githubusercontent.com/131929869/236675695-526a4f92-04a2-4249-8e06-3b57d7434fac.png)

![스image](https://user-images.githubusercontent.com/131929869/236675697-691d22da-1b02-4a24-936a-4b47fb40b2eb.png)


- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [4] 확인하기

![image](https://user-images.githubusercontent.com/131929869/236675559-bcc5b1a0-eae9-42d7-b802-c47ba48fa486.png)

>
 1️⃣ **`Win` + `R`**를 동시에 눌러 **실행** 도구를 엽니다.<br>
 2️⃣ **services.msc**를 입력하고 **확인**을 클릭합니다.

![image](https://user-images.githubusercontent.com/131929869/236675560-0af22658-f2ee-4faf-b668-73f33b9dceae.png)

>
 3️⃣ **서비스** 창이 열리면 설치할 때 입력되었던 서비스 명을 확인합니다.<br>
 [**[서비스 설정 가이드 이동하기]**](#서비스-등록-여부)

 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.