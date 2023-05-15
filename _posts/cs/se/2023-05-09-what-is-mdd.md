---
title: "[CS] MDD(Model Driven Development)"
excerpt: "Model-Driven Development (MDD): 모델 중심적 접근 방식으로 소프트웨어 개발 생산성 향상하기"
categories:
  - se
tags:
  - cs
  - se
  - lifecycle
  - mda
  - mdd

  
toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: "list"

date: 2023-05-09
last_modified_at: 2023-05-10
---

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [1] MDD의 개념

**MDD**는 **모델에 중점을 둔 개발 방법론**으로 모델을 이용하여 목표 **시스템을 단순화함**으로써,<br>
사용자는 **시스템을 쉽게 이해**할 수 있고 개발자는 **개발을 용이**하게 하는 것을 목적으로 한 개발 방법론입니다.
{:.notice}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] MDD의 특징

1. **모델 개발 중점**
    - **특징을 추출하여 단순화하는 표현 방식**<br>
        상위 · 하위 모델로 구분하며, 하위모델로 갈수록 구체적으로 표현합니다.
    - **사용자와 기술자가 소통할수 있는 언어로 표현**<br>
        일반적인 모델링 언어로는 UML, SQL, BPMN, ER-D 등이 있습니다.
    - **모델을 중심으로 분석, 설계를 수행하고, 이를 기반으로 소스코드 및 산출물을 자동으로 생성**<br>
        <u>프로그램 코드간의 변환을 자동화함</u>으로써 코드를 작성하는 번거로움과 오류 줄여 <u>생산성을 향상</u> 시킵니다.<br><br>
2. **개발 플랫폼에 종속되지 않는 메타모델 사용**
    - **MDD의 표준의 하나인 OMG의 MDA는 CIM, PIM, PSM을 정의하고 모델의 변환을 통해 소프트웨어를 생성**<br><br>
3. **모델간의 변환, 모델과 소스간의 변환을 구현하는 MDD 도구 지원 필수**<br><br>
4. **개발 참여자는 기존 프로젝트와 다른 역할을 부여**
    - **도메인 전문가, MDD 도구 개발자, 프레임워크 담당자 등 새로운 역할을 담당**<br>
        기본적으로 자동생성 구현을 위한 MDD 도구 개발자의 역할이 중요합니다.
    - **대형 SI 프로젝트의 경우, 모델러가 필요하고, 개발자의 비중보다 설계자의 비중이 커짐**<br>
        MDD에서는 <u>설계와 분석 단계의 구분이 어려우며, 설계와 동시에 개발,테스트가 진행</u>됩니다.


💡**MDA(Model Driven Architecture)란?**<br><br>
 : 
    ![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/148bf7d2-8f3f-41c2-843e-6d5bca224a0c){:.align-center}<br><br>
    **MDD에 대한 OMG(Object Management Group,객체 관리 그룹)에서 정의한 표준**
    - **CIM(Computation Independent Model)** : 하위 소프트웨어 구조와 관계없이 업무, 도메인에 대한 기능만을 정의합니다.
    - **PIM(Platform Independent Model)** : 구체적인 플랫폼과 관계없이 업무프로세스를 정의하며 변환 규칙이 생성되면, 여러 플랫폼에서 재사용 가능합니다.
    - **PSM(Platform Specific Model)** : PIM에서 자동 변환되는 IT기술에 종속되는 모델입니다.
{:.notice--info}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [3] MDD 등장 배경

기존 방법론에서는 분석, 설계, 구현, 테스트, 유지보수 등의 과정에서 많은 **<span style="color:#F25E34">인적자원과 시간, 비용이 소요</span>**되었으며,<br>
**<span style="color:#F25E34">개발자와 고객 사이의 의사소통</span>**이 원활하지 않아 **<span style="color:#F25E34">요구사항이나 변경사항에 대한 대응이 어렵다</span>**는 문제가 있었습니다.<br><br>
MDD의 출현 이전에도 **소프트웨어 개발 복잡성, 비용 증가, 의사소통를 해결을 위한 다양한 시도와 사례**가 있었습니다.
{:.notice}

- **구조적 방법론** : 절차적인 접근 방식으로 소프트웨어를 개발
    - 모듈화
    - 분할과 정복
    - 추상화
    - 구조화된 프로그래밍
- **객체지향 방법론** : 객체라는 개념을 중심으로 소프트웨어를 설계하고 개발하는 방식
    - 코드의 재사용
    - 유지보수성
    - 코드의 가독성
    - 다형성
    - 상속성
    - 캡슐화

그러나 이러한 방법론들은 **<span style="color:#F25E34">대규모 프로젝트에서 복잡도가 증가할수록 비용이 증가</span>**하는 문제가 있었습니다.<br>
또한, 이러한 방법론들은 **<span style="color:#F25E34">특정 플랫폼에 종속</span>**되는 경우가 많았기 때문에 이식성이 떨어지는 문제도 있었습니다.<br>
{:.notice}

- **구조적 방법론의 한계**
    - 대규모 소프트웨어에 적용하기 어려움
    - 유지보수 어려움
    - 새로운 요구사항 추가나 변경에 취약함

- **객체지향 방법론의 한계**
    - 객체 간의 관계가 복잡해질수록 디버깅이 어려워짐
    - 설계가 복잡해지고, 작은 프로그램에서는 오히려 비효율적일 수 있음
    - 상속, 다형성 등 개념의 이해가 어려울 수 있음


**위와 같은 한계와 문제에 대한 해결책으로 모델을 기반으로 소프트웨어를 개발하는 MDD가 나타났습니다.**
{:.notice}

- **MDD의 장점**
    - **<span style="color:#2cae67">높은 생산성</span>**<br>
        개발자가 비즈니스 요구사항을 바로 모델링하고 변환할 수 있으므로 개발 생산성이 높아집니다.
    - **<span style="color:#2cae67">높은 재사용성</span>**<br>
        모델 메타 모델을 기반으로 하므로, 다른 프로젝트에서도 모델을 재사용할 수 있습니다.
    - **<span style="color:#2cae67">간편한 유지보수</span>**<br>
        비즈니스 요구사항이나 프로젝트 요구사항이 변경되어도 모델만 수정하면 됩니다.
    - **<span style="color:#2cae67">개발과 디자인의 분리</span>**<br>
        모델링 도구를 사용하므로, 소프트웨어 개발과 디자인을 분리할 수 있습니다.
    - **<span style="color:#2cae67">자동화된 코드 생성</span>**<br>
        모델을 기반으로 코드를 자동 생성할 수 있으므로, 개발자가 직접 코드를 작성하는 데 필요한 시간과 비용을 절약할 수 있습니다.
    - **<span style="color:#2cae67">재사용 가능한 표준화된 모델</span>**<br>
        모델링 메타모델을 표준화하므로, 향후 다른 프로젝트에서 재사용할 수 있는 표준화된 모델을 만들 수 있습니다.
<br><br>

- **MDD의 제약요인**
    - **MDD 도구의 유연성 및 비용 산정 문제**<br>
        경영환경 대응 및 비용 효과 검증에 부족한 측면이 있어, <u>경영층이 적용을 결정하기 어려울 수 있습니다.</u>
    - **부족한 사용 사례**<br>
        사례가 많지 않아 <u>정보 공유 부족</u>합니다.<br>
        기술 문헌 및 연구가 많지 않아, <u>충분한 이해와 검증이 이루어지지 않은 상태</u>입니다.


![image](https://github.com/kunheelib/kunheelib.github.io/assets/131929869/1ef99bd2-d7d3-4e44-80f8-b4690beb1171){: .align-center width="90%"}

💡**알고가기**<br><br>
 : MDD 이전 유사한 개념으로 객체지향방법(OOM), 컴포넌트기반(CBD)이 있었습니다.<br>
OOM, CBD는 각각 객체, 컴포넌트가 추상화된 개념이기 보다는 **<u>코드 자체라는 측면에서 MDD와 구분</u>**됩니다.
{:.notice--info}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [4] MDD의 전망

- **MDD는 특정분야에서 있어 기능적인 유용성을 보임**
    - 설계와 개발이 동기화되어 문서 작성 및 유지보수 등에 도움을 줍니다.
    - 업무와 소프트웨어 개발을 모두 알아야하는 전문가의 수는 줄어들겁니다.
- **모바일, 클라우드 등의 영향으로 앞으로의 소프트웨어는 개발 주기가 점점 짧아지고, 개발 플랫폼도 급속도로 다양화해질 것으로 전망**
    - 이에 따라 도메인 기술이 축척된 애플리케이션을 보다 간단하고 다양하게 적용할 수 있는 MDD의 중요성이 커질 것으로 예상됨.
- **국내에 이미 다양한 분야에서 MDD 적용 시도되고 있음.**
    - 특히 은행 분야는 일부 성과를 보여줌.(LG CNS의 전북은행 프로젝트 사례)
- 앞으로 모델에 대한 다양한 사례와 시행착오가 축적이 되고, 개발 참여자들과 경영층의 이해가 증가하면서 MDD의 활용도도 증가할 것으로 예상

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [5] 요약

- MDD는 Model-Driven Development의 약자로 **소프트웨어 개발 방법론** 중 하나입니다.
- 모델을 기반으로 소프트웨어를 개발하며, 개발 생산성과 품질을 향상시킬 수 있습니다.
- MDD 방법론의 특징으로는 **모델 중심 개발, 재사용성, 유지보수 용이성, 시간 단축, 품질 향상** 등이 있습니다.
- 적용 사례가 더욱 많아진다면 개발 생산성과 품질 향상에 더 큰 기여를 할 것으로 예상됩니다.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# 참조

- [**소프트웨어정책연구소**](https://spri.kr/posts/view/13314?code=&study_type=&board_type=)
- [**OMG(Object Management Group)**](https://www.omg.org/mda/)

<!--
MDD,RAD,Low-Code

RAD는 개발자 중심
MDD는 비즈니스 중심

<https://modeling-languages.com/low-code-vs-model-driven/>
<https://modeling-languages.com/clarifying-concepts-mbe-vs-mde-vs-mdd-vs-mda/>
-->

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
이상 포스팅을 마치겠습니다.