---
title: "[Node.js] OpenAI API 사용하기"
excerpt: "Node.js에서 OpenAI API를 활용한 인공지능 개발하기"
categories:
  - nodejs
tags:
  - node
  - nodejs
  - express
  - generator
  - jade
  - openai
  - api
  - backend

toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: "list"

date: 2023-05-14
last_modified_at: 2023-05-14
---

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 준비하기

[**[OpenAI]**](https://openai.com/) 링크에 접속하여 이미지를 참고해주세요.
{: .notice}

## [1.1] OpenAI API Key 발급

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/7bd0e98e-6892-46c6-8848-c534186f6b5d)

>
 프로필을 클릭하고, **View API keys**를 클릭합니다

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/e40d040c-0746-4a08-a716-4dbd6919553a)

>
 **Create new secret key** 를 클릭합니다.

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/de04a187-2773-4f90-a4ac-2fd02ed93f90)

>
 생성할 key의 이름을 입력합니다.(선택사항으로서 입력하지 않아도 자동으로 입력됩니다.)

⚠️ **생성한 후 보여진 API Key를 꼭 복사해서 기억해주세요.**<br><br>
API Key는 다시 생성할 수 있으나, 한번 생성된 Key의 값은 **<u>최초에만 노출이 되고 그 이후에는 일부만 노출</u>**이 됩니다.
{: .notice--warning}

## [1.2] OpenAI organization Id 확인

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/73639902-d8f4-4d70-9ec7-4cc7ea1feac3)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 프로젝트 생성하기

이번 포스팅에서는 **express-generator**를 이용하여 개발환경을 구축하겠습니다.
{: .notice}

```terminal
npm install -g express-generator
```

💡**express-generator란?**<br><br>
 : express의  기본 구조를 생성해주는 템플릿 엔진입니다.<br>
 express [프로젝트명] 명령어를 통해 간편하게 프로젝트 구조를 생성할 수 있습니다.<br>
 자세한 내용은 [**express-generator이란?**]() 에서 자세한 설명을 작성하였으니 참고해주세요.
{:.notice--info}

```terminal
express [프로젝트명] --view=pug
```

>
 프로젝트를 생성합니다.
  : view는 pug(jade)를 사용으로 설정합니다 

```terminal
npm install dotenv --save
```

>
 API Key 값들을 저장 및 불러오기 위해 다운로드 받습니다.

```terminal
npm install openai --save
```

> 
 제일 중요한 부분입니다. openai npm을 꼭 다운 받아주세요.<br>
 [**[OpenAI API Reference]**](https://platform.openai.com/docs/api-reference)의 내용입니다.

## [2.1] .env 작성

**/.env**에 OpenAI에서 발급받은 코드를 복사하여 붙여넣습니다.

```
OPENAI_ORGANIZATION=Your KEY
OPENAI_SECRET_KEY=Your KEY
```

## [2.2] 미들웨어 작성

**/routes/users.js**에 아래 코드를 복사하여 붙여넣습니다.

```js
require('dotenv').config();                                 /* 작성한 .env의 API Key 값을 불러오기 위해 작성합니다.*/

var express = require('express');
var router = express.Router();

const { Configuration, OpenAIApi } = require("openai");     /* openai 모듈을 불러옵니다.*/

const callGpt35 = async (prompt) => {                   
  const configiration = new Configuration({         
    apiKey: process.env.OPENAI_SECRET_KEY,
    organization: process.env.OPENAI_ORGANIZATION,
  });
  try {
    const openai = new OpenAIApi(configiration);            /* openai에서 발급 받은 비밀키, 조직ID로 객체를 생성합니다 */

    const response = await openai.createChatCompletion({    /* 생성된 객체로 openAI의 여러가지 모델 중 하나인 gpt-3.5-turbo에 요청을 보냅니다. */
      model: "gpt-3.5-turbo",
      messages: [{ role: "user", content: prompt }],
    });
    return response.data.choices[0].message;

  } catch (error) {
      console.error('callGpt35() error >>> ', error);
      return null;
  }

};

/* GET users listing. */
router.get('/', function(req, res, next) {
  res.send('respond with a resource');
});

router.post('/chat', async (req, res) => {                  /* 해당 url(../user/chat)을 호출시 아래 코드가 실행됩니다. */
  const prompt = req.body.prompt;
  const response = await callGpt35(prompt);

  if(response){
    res.json({'response' : response});
  }else{
    res.status(500).json({'error' : 'Fail'})
  }
});

module.exports = router;

```

## [2.3] 화면 작성

**/views/index.jade**에 아래 코드를 복사하여 붙여넣습니다.

```
extends layout

block content
  #d0
    #d1
      #d11
        ol#items
    #d2
      #d21
        textarea#msgbox(name="msg", cols="30", rows="10" placeholder="메시지를 입력해주세요.")
      #d22
          input#sendBtn(type="button" value="전송")
          script(src='/javascripts/message.js')
          script.
            document.getElementById('sendBtn').addEventListener('click',function(){
              askBot();
            });

```

## [2.4] 이벤트 작성

**/public/javascripts/message.js**를 생성하여 아래 코드를 복사하여 붙여넣습니다.

```js
function addLine(writer, msg){                          /* html 코드를 생성합니다. */
    const ul = document.createElement('ul');
          ul.className = `msgbox ${writer}`
    const div = document.createElement('div');
    const p = document.createElement('p');
          p.innerHTML = `${msg}`;

    div.appendChild(p);
    ul.appendChild(div);

    document.getElementById('items').appendChild(ul);
}

function askBot(){                                      /* 전송 클릭시 실행될 함수 입니다. */
    const msgbox = document.getElementById('msgbox');
    const msg = msgbox.value;
    msgbox.value = '';
    msgbox.focus();

    addLine('me',msg);
    send(msg);
}
 
async function send(msg){                               /* 미들웨어에서 생성한 내용을 호출합니다. */
    try {
        const response = await fetch("../users/chat",{
            method : "post",
            headers : {
                "Content-Type" : "application/json",
            },
            body : JSON.stringify({"prompt": msg}),
        });

        const prediction = await response.json();   
        addLine('bot', prediction.response.content);
    } catch(error){
        console.error("send() Error!!");
    } finally{

    }
}
```

## [2.5] 스타일 작성

**/public/stylesheets/style.css**에 아래 코드를 복사하여 붙여넣습니다.

```css
body {
  padding: 50px;
  font: 30px "Lucida Grande", Helvetica, Arial, sans-serif;
  background-color: #343541;
}

a {
  color: #00B7FF;
}

textarea#msgbox {
  width: 95%;
  height: 1rem;
  resize: none;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
  line-height: 1;
}

input#sendBtn {
  width: 100%;
}

#d0 {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;}

#d1 {
  flex-grow: 1;}

#d2 {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  display: flex;
  justify-content: space-between;
}

#d21{
  width: 100%;
}

#d22 {
  display: flex;
  justify-content: center;
  align-items: center;
}

#sendBtn {
  padding: 10px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  transition: background-color 0.2s ease-in-out;
}

#sendBtn:hover {
  background-color: #388e3c;
}

ol#items {
  list-style: none;
  margin: 0;
  padding: 0;
}

.me {
  background-color: #343541;
  color:#f6f6f6;
}

.bot {
  background-color: #444654;
  color:#f6f6f6;
}
```

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 확인하기

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/c96196a5-4e81-4165-ac40-4d77d21baba4)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.