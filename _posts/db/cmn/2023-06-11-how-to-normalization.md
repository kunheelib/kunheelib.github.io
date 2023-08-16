---
title: "[Database] 데이터베이스 정규화하기"
excerpt: "데이터베이스 정규화 방법: 이해하기 쉽고 유지보수 가능한 데이터 모델링"
categories:
  - db-cmn
tags:
  - db
  - normalization
  - 정규화

toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: "list"

date: 2023-08-16
last_modified_at: 2023-08-16
---

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] 정규화란?

관계형 데이터베이스의 설계에서 중복을 최소화하게 데이터를 구조화하는 프로세스를 정규화라고 합니다.

## [1.1] 정규화의 목표

데이터의 **중복을 최소화**화고, 데이터베이스의 **구조를 최적화**하여 **데이터의 일관성, 무결성, 유지보수성을 향상**시키는 것입니다.
{:.notice}

## [1.2] 정규화의 필요성

### [1.2.1] 이상현상(Anomaly)

1. **<span style="color:#F25E34">삽입 이상(Insertion Anomaly)</span>**<br>
  테이블의 일부 속성에만 값을 삽입하려할 때, 해당 테이블의 다른 속성들은 NULL 값이나 임의의 값을 가져야합니다.

2. **<span style="color:#F25E34">갱신 이상(Update Anomaly)</span>**<br>
  동일한 데이터가 여러 행에 중복되어 있을 경우, 하나의 행만 갱신하고 나머지 중복된 행들은 갱신되지 않는 경우가 있습니다.

3. **<span style="color:#F25E34">삭제 이상(Deletion Anomaly)</span>**<br>
  특정 데이터를 삭제하기 위해 해당 데이터가 포함된 행을 삭제하면, 그 행과 관련된 다른 데이터들도 함께 삭제되어 데이터의 손실이 발생할 수 있습니다.

위와 같은 문제들이 데이터의 중복과 비일관성을 유발하여 데이터베이스의 정확성과 성능을 저하시킬 수 있습니다.
데이터베이스 정규화를 통해 **구조를 최적화**하여 이상현상을 방지하고, **데이터의 일관성** 및 **무결성을 유지**할 수 있습니다.


### [1.2.2] 함수 종속성(Functional Dependency)

데이터베이스에서 한 속성의 값이 다른 속성의 값에 종속되는 관계를 의미합니다.
다시 말해, 하나의 속성의 값이 결정되면 다른 속성의 값도 결정될 수 있는 관계입니다.

 A → B 로 표현하며
 A는 결정자, B는 종속자라고 합니다.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 정규화의 장단점

## [2.1] 장점

1. 최소의 데이터로 최적의 데이터베이스 구축 및 데이터 중복성 제거
2. 중복 최소화로 인한 저장공간의 효율성
3. 데이터베이스 변경으로 인한 이상현상 제거
4. 데이터 구조의 안정성 및 무결성 유지

## [2.2] 단점

1. 릴레이션 간의 JOIN 연산 증가로 인한 응답 시간 저하


- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] 정규화 과정

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/1bcab7b3-d799-4576-bcf5-06250c0b16ac)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/01adf1a2-2919-4153-b1ac-cbff458f42a8)

본 포스팅에서는 BCNF 과정까지의 내용을 다룹니다.

아래 사진은 과정을 진행하기에 앞서 사용할 테이블 정보입니다.

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/dcb0931d-bead-4df9-bf64-d3bddb2665eb)

## [3.1] 제 1 정규형(1NF)

📌 **제 1 정규형(1NF)**<br><br>
**각 컬럼이 하나의 속성**만을 가져야한다.<br>
하나의 컬럼은 같은 종류나 타입의 값을 가져야한다.<br>
각 컬럼이 유일한 이름을 가져야한다.<br>
컬럼의 순서가 상관없어야한다.
{:.notice--primary}

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/d3476705-1c9b-47da-98ea-c663ed9f87eb)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/c4a3d480-12b2-47cf-b7b7-8296841ee345)

## [3.2] 제 2 정규형(2NF)

📌 **제 2 정규형(2NF)**<br><br>
제 1 정규형을 만족해야한다.<br>
모든 컬럼이 **부분적 종속이 없어야 한다.** 즉, 모든 컬럼이 **완전 함수 종속을 만족**해야한다.<br>
{:.notice--primary}

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/b0da690e-ccf0-4b13-bd69-afb34834d13f)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/db281dee-add2-452e-9080-2ba5f528ef9d)

## [3.3] 제 3 정규형(3NF)

📌 **제 3 정규형(3NF)**<br><br>
제 2 정규형을 만족해야한다.<br>
기본키를 제외한 속성들 간의 **이행 종속성이 없어야한다.**<br>
{:.notice--primary}

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/f4733a98-4c94-42c6-8202-0098c99fb277)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/27e1649d-1cb6-4906-9610-3348e4efa91e)

## [3.4] BCNF(Boyce-Codd Normal Form)

📌 **BCNF(Boyce-Codd Normal Form)**<br><br>
제 3 정규형을 만족해야한다.<br>
모든 결정자가 후보키 집합에 속해야한다.<br>
{:.notice--primary}

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/6ec5e281-cfdb-4f70-80f3-7078a625c3a5)

![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/69602d67-2901-4acf-9468-27111f6ac8e4)

<!--
## [3.5] 제 4 정규형(4NF)

📌 **제 4 정규형(4NF)**<br><br>
  : BCNF를 만족해야한다.<br>
 다치 종속이 없어야한다.<br>
{:.notice--primary}

## [3.6] 제 5 정규형(5NF)

📌 **제 5 정규형(5NF)**<br><br>
  : 제 4 정규형을 만족해야한다.<br>
 조인 종속이 없어야한다.<br>
 조인 연산을 했을 때 손실이 없어야한다.<br>
{:.notice--primary}
-->
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

