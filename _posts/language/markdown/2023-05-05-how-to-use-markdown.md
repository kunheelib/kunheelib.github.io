---
title: "[Language] Markdown(마크다운) 사용법"
excerpt: "Markdown 사용법: 기본 문법부터 확장 기능까지"
categories:
  - markdown
tags:
  - markdown
  - md

toc: true
toc_sticky: true
toc_label: "사용법"
toc_icon: "list"

date: 2023-05-05
last_modified_at: 2023-05-06
---
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 제목(Header)

**< 예시 >**

```markdown
# 제목 1        <!--  <h1> -->
## 제목 2       <!--  <h2> -->
### 제목 3      <!--  <h3> -->
#### 제목 4     <!--  <h4> -->
##### 제목 5    <!--  <h5> -->
###### 제목 6   <!--  <h6> -->
```
```markdown
제목 1
===             <!--  <h1> -->
제목 2
---             <!--  <h2> -->
```

**< 결과 >**

(예시)제목 2 
---
### (예시)제목 3
#### (예시)제목 4
##### (예시)제목 5
###### (예시)제목 6

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 목록(List)

**< 예시 >**

```markdown
1. 정렬 목록 <!-- <ol> <li></li><li></li>... <ol> -->
2. 정렬 목록
 - 비정렬 목록 <!-- <ul> <li></li><li></li>... <ul> -->
  * 비정렬 목록
   + 비정렬 목록
3. 정렬 목록

1. 정렬 목록 <!-- 문단을 띄워져도 구조의 영향이 가지 않는다면 연번을 유지합니다. -->
```

**< 결과 >**

1. 정렬 목록 
2. 정렬 목록
 - 비정렬 목록 
  * 비정렬 목록
   + 비정렬 목록
3. 정렬 목록

1. 번호 목록

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 테이블(Table)

**< 예시 >**

```markdown
| 컬럼명 | 컬럼명 | 컬럼명 | 컬럼명 |
| :----- | -----: | :-----: | --- |<!-- :(콜론) 위치에 따른 정렬 -->
| 데이터 | 데이터 | 데이터 | |
```

**< 결과 >**

| 사원번호 | 성명 | 연봉 | 주소 | 비고 |
| :---: | :---: | ---: | :--- | :---: |
| 100001 | 박사장 | 500,000,000 | 서울시 용산구 | `CEO` |
| 200001 | 박전무 | 400,000,000 | 서울시 강남구 | `COO` |
| 200002 | 박이사 | 400,000,000 | 서울시 종로구 |  |
| 300001 | 류부장 | 400,000,000 | 서울시 서초구 |  |
| 500001 | 이대리 | 20,000,000 | 서울시 강서구 | 오늘 점심 뭐먹지? |

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 강조(Emphasis)

**< 예시 >**

```markdown
*기울임체* <!-- <em> -->
_기울임체_ <!-- <em> -->

**굵게** <!-- <strong> -->
__굵게__ <!-- <strong> -->

~~취소선~~ <!-- <del> -->

<u>밑줄</u> <!-- <u> -->
```

**< 결과 >**

*기울임체*<br>
_기울임체_<br>
**굵게**<br>
__굵게__<br>
~~취소선~~<br>
<u>밑줄</u>

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 줄바꿈(Line Breaks)

**< 예시 >**

```markdown
1번째줄
2번째줄<br>
3번째줄(스페이스바 두번)
4번째
```

**< 결과 >**

1번째줄
2번째줄<br>
3번째줄  
4번째줄

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# 수평선(Horizontal Rule)

**< 예시 >**

```markdown
- - - <!-- <hr> -->
* * * <!-- <hr> -->
_ _ _ <!-- <hr> -->
```

**< 결과 >**

- - -
* * *
_ _ _

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 코드(Code)

**< 예시 >**

~~~markdown
<!-- <code> -->
`속성`

<!-- <code> -->
```확장자[예: java, js, md ...]
코드 내용
```
~~~
```
~~~확장자[예: java, js, md ...]
코드 내용
~~~
```

**< 결과 >**

 `속성`
 ```js
  const hello = () => {
    console.log("Hello Wolrd");
  };
  hello();
 ```
 ~~~java
  public static void main(String[] arg[]){
    System.out.println("Hello World");
  } 
 ~~~

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 인용문(BlockQuote)

**< 예시 >**

```markdown
<!-- <pre> -->
> 인용문
>> 중첩 인용문
>>> 중첩 인용문
>>>> 중첩 인용문
```

**< 결과 >**
- - -
 > Watch your thought for they become words.<br>
 >> Watch your words for they become actions.<br>
 >>> Watch your actions for they become habits.<br>
 >>>> Watch your habits for they become your character.<br>
 >>>>> and Watch your character, for it becomes your destiny.<br>
 >>>>>> What we think, we become.<br><br>
-**The Iron Lady**, Margaret Thatcher

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 링크(Links)

**< 예시 >**

```markdown
<!-- <a> -->
[명칭](https://link.com "설명")

링크 : <https://link.com>

[명칭](#제목1)

[변수]: https://link.com <!-- 화면에는 노출되지 않습니다. -->
```

**< 결과 >**

 [**개발자 거니 Blog**](https://kunheelib.github.io/ "끄적끄적")<br><br>
 개발자 거니 Blog : **<https://kunheelib.github.io/>**<br><br>
 [**메뉴 최상단으로 이동하기**](#제목header)<br><br>
 Markdown 사용법은 **[여기]**를 클릭
 
 [여기]: https://kunheelib.github.io/

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 이미지(Images)

**< 예시 >**

```markdown
<!-- <img> -->
![명칭](https://link.com/image.jpg "설명"){:기타 속성(크기,위치,... 등등)}

![명칭][변수]{:기타 속성(크기,위치,... 등등)}

[변수]: https://link.com/image.jpg "설명" <!-- 화면에는 노출되지 않습니다. -->
```

**< 결과 >**

![에그](https://user-images.githubusercontent.com/131929869/236434146-32d62c44-6ea6-4209-8c4a-fb56356bc670.jpg "우리집 고양이 츄르를 좋아해"){: .align-center width="60%"}

![감성][피렌체]{: .align-center width="50%"}

[피렌체]: https://user-images.githubusercontent.com/131929869/236434148-d42ead91-b68a-4b4c-90e2-a371f6f07c5d.jpg "감성카페"

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
## 이미지 링크

**< 예시 >**

```markdown
[![명칭](https://link.com/image.jpg "설명"){:기타 속성(크기,위치,... 등등)}](https://link.com)
```

**< 결과 >**

[![에그](https://user-images.githubusercontent.com/131929869/236434146-32d62c44-6ea6-4209-8c4a-fb56356bc670.jpg "바보야"){: .align-center width="60%"}](https://kunheelib.github.io/)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.