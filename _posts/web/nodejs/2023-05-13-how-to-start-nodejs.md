---
title: "[Node.js] Node.js 프로젝트 만들기"
excerpt: "간단한 Node.js 프로젝트 만들기: 초보자를 위한 가이드"
categories:
  - nodejs
tags:
  - node
  - node.js
  - npm
  - backend

toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: "list"

date: 2023-05-13
last_modified_at: 2023-05-13
---

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 프로젝트 초기화

⚠️ **프로젝트를 초기화하기 전에 시작할 위치로 이동 후 진행해주세요!**<br><br>
 : 다양한 명령어를 통해 프로젝트에 필요한 파일들을 생성하게 되는데 현재 위치한 폴더를 기준으로 생성하게 됩니다.<br>
 따라서 원하지 않은 위치에 프로젝트에 필요한 파일이 생성될 수 있으니 꼭 시작할 위치로 이동해주세요.
{: .notice--warning}

```terminal
npm init -y
```

>
 **package.json**을 생성하여 npm을 쓸 수 있는 초기 환경을 설정해줍니다.<br>
 (**`-y`** 옵션을 넣게되면 default값으로 설정됩니다.)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/f6839d18-a02c-41f2-b90d-d70a42db6440)

💡**package.json란?**<br><br>
 : 프로젝트의 정보와 의존성을 관리하는 파일입니다.<br>
{: .notice--info}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 모듈 설치

## [2.1] express

💡**express란?**<br><br>
 : http와 같은 서버 모듈로서, 간단한 코드로 웹 서버의 기능을 구현할 수 있고,<br>
미둘웨어와 라우터를 사용하여 편리하게 웹 서버를 구성할 수 있습니다.
{: .notice--info}

```terminal
npm install express --save
```

>
 **`--save`** 옵션을 넣게되면 **package.json**의 **dependencies** 항목에 모듈을 추가한다는 의미입니다.<br>
 <u>npm 5.0 이후 버전에서는 기본 옵션으로 적용되어 있어 생략해도 무방</u>합니다.

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/00ca5861-cc59-4bf2-9e41-7b8828cec0bc)

💡**package-lock.json란?**<br><br>
 : **package.json**파일에 있는 패키지들의 의존 관계와 정확한 버전 정보를 저장합니다.<br>
 `npm install <package>` 명령어로 생성된
 node_modules 폴더에 설치된 패키지들의 정보를 저장합니다.
{: .notice--info}

## [2.2] ejs

💡**ejs란?**<br><br>
 : Embedded javascript의 약자로, 자바스크립트가 내장되어 있는 html 모듈입니다.<br>
html 안에서 **`<% %>`**, **`<%= %>`**를 이용하여 서버의 데이터나 코드를 실행할 수 있게 해줍니다.
{: .notice--info}

```terminal
npm install ejs
```

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/3d16af42-18cb-4300-b6aa-f9d981cb54dc)

## [2.3] dotenv

💡**dotenv란?**<br><br>
 : **환경변수를 .env파일에 저장**하고 **`process.env`**로 로드하는 의존성 모듈입니다.<br>
  쿠키 인증에 쓰이는 비밀키 값을 그대로 쓰게되면 보안에 취약한 문제점이 생기는데<br>
  **.env** 파일에 작성하여 **`process.env`**로 읽게되면 **취약점을 해결**할 수 있습니다.<br>
  주로 API키, 비밀번호 등 노출되면 안되는 중요한 키값들을 정의합니다.
{: .notice--info}

```terminal
npm install dotenv
```

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/6b83ce33-6013-4cf1-8132-1e08a84a53ba)

### [2.3.1] .env 생성하기

```xml
YOUR_API_KEY=VALUE
```

>
 위와 같은 코드 형식으로 자신에게 필요한 내용을 기재합니다.(본 포스팅에서는 사용하지 않겠습니다.)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/7a67915a-505d-40a6-9980-ca2a1d437679)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 파일 생성

## [3.1] app.js

💡**app.js란?**<br><br>
: **일반적으로 애플리케이션의 진입점(Entry Point)이라고 표현합니다.**<br>
 **app.js** 파일에서는 애플리케이션을 초기화하고 실행하기 위한 설정과 코드를 작성합니다.<br>
 이를 통해 Node.js 애플리케이션을 시작하고, 요청을 받아들이고, 처리하고, 응답을 보내는 등의 작업을 수행할 수 있습니다.<br>
 또한 필요한 모듈을 불러오고, 이를 이용하여 웹 서버를 생성하고, 라우팅 설정을 하고, 미들웨어를 추가하는 등의 작업을 수행합니다.<br>
 이를 통해 Node.js 애플리케이션의 동작을 제어하고, 기능을 확장할 수 있습니다.
{: .notice--info}

```javascript
const express = require('express')
const app = express();
const port = 3000;

app.set("views", "./views");
app.set("view engine","ejs");

app.get("/", (req,res) =>{
    res.render("home/index");
});

app.listen(port,() => {
    console.log(
`####################################################################################
                                    RUNNIG NODE.JS
####################################################################################`);

});
```

>
 **루트(/)**에 app.js를 생성하고 위 코드를 복사하여 붙여 넣습니다.

## [3.2] index.js

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>Hello kunheelib!</h1>
</body>
</html>
```

>
 **루트(/)**에 views/home/index.js를 생성하고 위 코드를 복사하여 붙여 넣습니다.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [4] 확인하기

```terminal
node app.js
```
![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/63485ebc-8e10-49a6-b4be-3f77e60f7301)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/65e3f3aa-7df2-4fcd-8866-ebc1ca09b33c)


- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.