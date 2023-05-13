---
title: "[IntelliJ] Maven & Spring 프로젝트 만들기"
excerpt: "IntelliJ에서 Maven과 Spring을 활용한 프로젝트 생성하기"
categories:
  - tool
tags:
  - maven
  - spring
  - spring mvc
  - intellij
  - tomcat

toc: true
toc_sticky: true
toc_label: "목차"
toc_icon: ""

date: 2023-05-08
last_modified_at: 2023-05-09
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
# [1] 프로젝트 생성 - Maven

![image](https://user-images.githubusercontent.com/131929869/236712650-3cef5a82-8805-4001-a520-a9c6fdb5f337.png)

>
 **Create New Project**를 클릭합니다.<br><br>

💡**이미 기존 프로젝트가 열려 있는 경우**<br><br>
 : 화면 상단에 **File > New > Project**를 선택하시면 됩니다.<br>
만약 동일하게 진행하고자 한다면 **File > Close Project**를 클릭해서 이미지와 동일한 화면을 확인할 수 있습니다.
{:.notice--info}
  
![image](https://user-images.githubusercontent.com/131929869/236713521-0ca758c9-09d1-40f3-b8e5-20e7aae10125.png)

>
 좌측의 프로젝트 목록에서 **Maven**을 클릭해주세요.
>
 **Project SDK**를 사용할 **jdk**로 선택해주세요.

![image](https://user-images.githubusercontent.com/131929869/236720060-e0d6fdf3-5fc9-43ee-a345-8ed5ec514e83.png)

>
 **Name**의 내용을 입력해주세요.
  : 입력시 **Location**,**ArtifactId**이 같이 변경됩니다.
>
 **Location**의 위치를 확인해주세요.<br>
>
 **GroupId**의 내용을 입력해주세요.

💡**알고가기**<br><br>
 : 
  🔹**`GroupId`** : 프로젝트를 식별해주는 고유 ID 입니다.<br>
  🔹**`ArtifactId`** : 해당 프로젝트를 식별하는데 사용됩니다.(빌드되어 생성되는 jar파일의 이름과 관련)<br>
  🔹**`Version`** : 프로젝트 또는 라이브러리의 현재 버전을 나타냅니다.<br><br>
**Maven**에서는 라이브러리를 다룰 때, **<u>GroupId, ArtifactId, Version 정보를 함께 사용</u>**합니다.<br>
**Version**에서 작성되었던 **<u>1.0-SNAPSHOT의 의미는 아직 개발 중인 버전</u>**을 뜻합니다.<br>
기본적으로 pom.xml 파일에서 version 항목을 1.0-SNAPSHT으로 설정합니다.<br>
{: .notice--info}

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
# [2] 프레임워크 추가 - Spring MVC

![image](https://user-images.githubusercontent.com/131929869/236713324-2f1ba707-834a-43ff-b478-9015e4e87919.png)

>
 좌측의 생성된 프로젝트를 **마우스 우클릭 > Add Framework Support...** 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236723267-8cbc6135-c31f-4c1c-9cf8-657495dd9325.png)

>
 좌측의 프레임워크 목록에서 **Spring > Spring MVC**를 선택하고 **OK**를 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236723800-6fdc36eb-705e-41ef-ab83-21e32ae0cc96.png)

>
 **web 디렉터리와 파일들이 생성된 걸 확인합니다.**

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [3] 서버 설정 - Tomcat

📌 **현 단계를 수행하기에 앞서 Tomcat 설치되어 있어야합니다.**<br>
설치방법은 [**[Tomcat 설치하기]**](https://kunheelib.github.io/)에 포스팅을 참고해주세요.
{: .notice--primary}

![image](https://user-images.githubusercontent.com/131929869/236729908-0fdaf8c3-6ee4-4790-8690-6046e6a99bfd.png)

>
 화면 상단에 있는 **Add Configuration...**을 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236730202-ba219926-f462-4698-87ef-852132a35a3b.png)

>
 좌측의 구성 목록에서 **Tomcat Server > Local**을 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236730640-2df70b56-8597-4f5b-97f1-fbb0ff0c57b4.png)

>
 **Application server**를 설치되어 있는 **Tomcat**을 선택해주세요.
>
 **Fix**를 클릭해주세요.

💡**알고가기**<br><br>
 : 
  🔹**Fix**를 클릭시 IntelliJ가 서버 구성 문제를 **<u>자동으로 분석하여 해당 문제를 수정하거나 조치할 수 있는 방법을 제안</u>**해줍니다.
{: .notice--info}

![image](https://user-images.githubusercontent.com/131929869/236731399-9d804ee9-4e47-45a6-b924-9c852b7c1a2c.png)

>
 **Application context**를 **루트(/)**로 설정합니다.(기본값)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [4] 플러그인 설정 - Lombok

💡**Lombok(롬북)이란?**<br><br>
 : **Java**의 라이브러리 중 하나로, **<u>반복적이고 지루한 코드 작성을 줄여주는 간편한 방법을 제공</u>**해줍니다.<br>
 **Getter, Setter, Construcctor 등** 코드를 직접 작성하지 않고 어노테이션(@)을 이용해 자동으로 생성해줍니다.
{: .notice--info}

![image](https://user-images.githubusercontent.com/131929869/236731750-af29ca35-ad33-4907-b191-5b2dc536c888.png)

>
 **`Ctrl` + `Alt` + `S`** 동시에 눌러 **Setting** 창를 열고 **Plugins**를 클릭해주세요.
>
 검색창에 **Lombok**을 검색하여 설치해주세요.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [5] 데이터베이스 설정 - MySQL

📌 **현 단계를 수행하기에 앞서 MySQL이 설치되어 있어야합니다.**<br><br>
설치방법은 [**[MySQL 설치하기]**](https://kunheelib.github.io/mysql/install-mysql/)에 포스팅을 참고해주세요.
{: .notice--primary}

![image](https://user-images.githubusercontent.com/131929869/236735583-420d5ff9-3f3a-4dda-b529-f994a47d890f.png)

>
 **`Ctrl` + `Alt` + `Shift` + `S`** 동시에 눌러 **Project Structure**창을 열고 **Libraries**를 클릭해주세요.
>
 화면 중간에 있는 **`+`** 버튼을 클릭 후 **Java**를 클릭해주세요.

![image](https://user-images.githubusercontent.com/131929869/236735916-37daeb3d-a461-4e1c-bd49-13c2cc424d5c.png)

>
 **C:\Program Files(x86)\MySQL\Connector J 8.0** 에서 **mysql-connector-j-8.0.x.jar** 파일을 선택합니다.

![image](https://user-images.githubusercontent.com/131929869/236736263-027de7da-49f0-4ebf-9cb6-9a268b947f8a.png)

>
 **적용할 프로젝트를 선택합니다.**

![image](https://user-images.githubusercontent.com/131929869/236736266-c8b845ba-782b-412b-8ed3-1e3e899723ba.png)

>
 **추가된 라이브러리를 확인합니다.**

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [6] 메이븐 설정 - pom.xml
💡**알고가기**<br><br>
 : 
  🔹**Maven이란?**<br>
     Java 기반 프로젝트 빌드, 배포, 관리를 위한 도구입니다.<br>
     Maven을 사용하면 프로잭트 개발을 위한 의존성 관리, 빌드, 테스트, 배포, 문서화 등을 편리하게 수행할 수 있습니다.<br><br>
  🔹**pom.xml이란?**<br>
     Project Object Model의 약어로 프로젝트를 구성하며, 이를 통해 프로젝트 설정하고 빌드 프로세스를 관리합니다.
{: .notice--info}

![image](https://user-images.githubusercontent.com/131929869/236740645-03ff6ca6-ca19-47ae-a0ef-d04a07f91de5.png)

>
 좌측의 디렉터리에서 **pom.xml**을 열어주세요.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>org.kunheelib</groupId>
    <artifactId>spring-project</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <java-version>1.8</java-version>
        <org.springframework-version>5.2.3.RELEASE</org.springframework-version>
        <org.aspectj-version>1.9.0</org.aspectj-version>
        <org.slf4j-version>1.7.36</org.slf4j-version>
        <log4j-version>1.2.17</log4j-version>
    </properties>

    <dependencies>
        <!--springframework-->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context</artifactId>
            <version>${org.springframework-version}</version>
            <exclusions>
                <exclusion>
                    <groupId>commons-logging</groupId>
                    <artifactId>commons-logging</artifactId>
                </exclusion>
            </exclusions>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
            <version>${org.springframework-version}</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-test</artifactId>
            <version>${org.springframework-version}</version>
        </dependency>

        <!--aspectj-->
        <dependency>
            <groupId>org.aspectj</groupId>
            <artifactId>aspectjrt</artifactId>
            <version>${org.aspectj-version}</version>
        </dependency>

        <!--slf4j-->
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-api</artifactId>
            <version>${org.slf4j-version}</version>
        </dependency>
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>jcl-over-slf4j</artifactId>
            <version>${org.slf4j-version}</version>
            <scope>runtime</scope>
        </dependency>
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-log4j12</artifactId>
            <version>${org.slf4j-version}</version>
            <scope>runtime</scope>
        </dependency>
        <!--log4j-->
        <dependency>
            <groupId>log4j</groupId>
            <artifactId>log4j</artifactId>
            <version>${log4j-version}</version>
            <exclusions>
                <exclusion>
                    <groupId>javax.mail</groupId>
                    <artifactId>mail</artifactId>
                </exclusion>
                <exclusion>
                    <groupId>javax.jms</groupId>
                    <artifactId>jms</artifactId>
                </exclusion>
                <exclusion>
                    <groupId>com.sun.jdmk</groupId>
                    <artifactId>jmxtools</artifactId>
                </exclusion>
                <exclusion>
                    <groupId>com.sun.jmx</groupId>
                    <artifactId>jmxri</artifactId>
                </exclusion>
            </exclusions>
        </dependency>

        <!--servlet-->
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>4.0.1</version>
        </dependency>
        <dependency>
            <groupId>javax.servlet.jsp</groupId>
            <artifactId>jsp-api</artifactId>
            <version>2.1</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>jstl</artifactId>
            <version>1.2</version>
        </dependency>

        <!--junit-->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.12</version>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <version>1.18.0</version>
            <scope>provided</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>2.5.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                    <compilerArgument>-Xlint:all</compilerArgument>
                    <showWarnings>true</showWarnings>
                    <showDeprecation>true</showDeprecation>
                </configuration>
            </plugin>
        </plugins>
    </build>

</project>
```

![image](https://user-images.githubusercontent.com/131929869/236740977-8bc528f6-5814-4afe-947c-7db816a01089.png)

>
 위 코드를 복사하여 **pom.xml**에 붙여넣은 후 저장합니다.
>
 화면 우측에 있는 **Maven**을 클릭 후 **clean** 및 **compile**을 클릭합니다.

![image](https://user-images.githubusercontent.com/131929869/236741819-86c788aa-d830-46bc-be72-7424ad0b6a8f.png)

>
 **`Ctrl` + `Alt` + `Shift` + `S`** 동시에 눌러 **Project Structure**창을 열고 **Artifacts**를 클릭해주세요.<br>
 Output Layout 탭의 Available Elements를 확인합니다.
>
 보여진 모든 항목들을 **`더블클릭`**하여 추가해주세요.

![image](https://user-images.githubusercontent.com/131929869/236742129-977eb211-7ce3-41a7-b8d6-530a1afb68ca.png)

>
  **추가된 라이브러리를 확인합니다.**

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [7] 로그 설정 - log4j.xml

>
 좌측의 디렉터리에서 **src/main/resources**에 **log4j.xml** 파일을 생성해주세요.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE log4j:configuration PUBLIC "-//APACHE//DTD LOG4J 1.2//EN" "log4j.dtd">
<log4j:configuration xmlns:log4j="http://jakarta.apache.org/log4j/">

    <appender name="console" class="org.apache.log4j.ConsoleAppender">
        <param name="Target" value="System.out" />
        <layout class="org.apache.log4j.PatternLayout">
            <param name="ConversionPattern" value="%-5p: %c - %m%n" />
        </layout>
    </appender>

    <logger name="org.springframework.core">
        <level value="info" />
    </logger>

    <logger name="org.springframework.beans">
        <level value="info" />
    </logger>

    <logger name="org.springframework.context">
        <level value="info" />
    </logger>

    <logger name="org.springframework.web">
        <level value="info" />
    </logger>

    <root>
        <priority value="info" />
        <appender-ref ref="console" />
    </root>

</log4j:configuration>
```

>
 위 코드를 복사하여 **log4j.xml**에 붙여넣은 후 저장합니다.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [8] 테스트

## [8.1] 데이터베이스

![image](https://user-images.githubusercontent.com/131929869/236760494-c92e2d61-ba95-40be-be8e-0a9c286e108c.png)

```java
import lombok.extern.log4j.Log4j;
import org.junit.Test;

import java.sql.Connection;
import java.sql.DriverManager;

import static org.junit.Assert.fail;

@Log4j
public class JdbcConnectTest {
    static {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    @Test
    public void connection() {
        try(Connection conn = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306", "root", "비밀번호")) {
            log.info(conn);
        } catch (Exception e) {
            fail(e.getMessage());
        }
    }
}
```

>
 좌측의 디렉터리에서 **src/test/java/**에 **JdbcConnectTest.java** 파일을 생성 후,<br>
 위 코드를 복사해서 생성한 **JdbcConnectTest.java**에 붙여넣어주세요.<br>
>
  **테스트를 실행 후 정상일 경우 log에서 같은 내용을 확인할 수 있습니다.**

## [8.2] Spring

![image](https://user-images.githubusercontent.com/131929869/236754477-11da5b63-7e66-4dec-a81f-044f50a6a057.png)

>
 좌측의 디렉터리에서 **web/WEB-INF/**에서 **web.xml** 열고 `<url-pattern>`의 내용을 루트(/)로 입력해주세요.

![image](https://user-images.githubusercontent.com/131929869/236754512-93743027-f62d-46ad-8c2c-b231c0d29f7c.png)

```java
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
@RequestMapping("/home/*")
public class HomeController {

    @GetMapping("test")
    public @ResponseBody String homeTest() {
        return "Maven & Spring Create Project Success!!";
    }
}
```

>
 좌측의 디렉터리에서 **src/main/java/**에 **com.kunheelib.controller** 패키지를 추가해주세요.<br>
 (<u> 고정된 값이 아니기에 원하는 내용으로 작성하시면 됩니다. </u>)
>
 생성된 패키지에 **HomeController.java** 파일을 생성한 후,<br>
 위 코드를 복사해서 생성한 **HomeController.java**에 붙여넣어주세요.<br>
 (<u> package 정보까지 제거하시면 안됩니다. </u>)
 

![image](https://user-images.githubusercontent.com/131929869/236754541-ce75648c-1e9a-4197-8d12-f7312cbc6bd8.png)

```xml
<context:component-scan base-package="com.kunheelib.controller" />
```

>
 좌측의 디렉터리에서 **web/WEB-INF/**에서 **dispatcher-servlet.xml** 열고 위 코드를 복사해서 붙여넣어주세요.

![image](https://user-images.githubusercontent.com/131929869/236759341-68663094-cf06-4c99-9998-71fc13e1a20b.png)

>
 Tomcat을 실행 후 열린 브라우저에서 **localhost:8080/home/test**를 입력하면<br>
 **정상일 경우 위 이미지와 같은 내용을 확인할 수 있습니다.**

⚠️ **bean 설정이 모두 되어 있는지 확인해주세요.**<br><br>
bean을 등록하기 위해 **dispatcher-servlet.xml** 에 **`<context:component-scan>`**을 작성했습니다.<br>
이 코드를 사용하려면 파일 상단 **`<beans>`**에 네임스페이스와 스키마를 선언해야합니다.<br><br>
 : **[작성 방식]** <br>
    - 네임스페이스 : xmlns:접두사="네임스페이스 URI" 형태로 선언합니다.<br>
    - 스키마: xsi:schemaLocation 속성안에 기재하며, {네임스페이스 URI(위치)} {스키마 파일}을 규칙으로 항상 짝수를 유지해야합니다.
{: .notice--warning}

```xml
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
       http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">
```

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# [9] 한글 설정

![image](https://user-images.githubusercontent.com/131929869/236754283-865311c2-25ce-4ca3-85d7-427166aefa26.png)

**위 이미지처럼 한글이 깨져서 나오는 경우 아래 설정을 따라주세요.**
{:.notice}

![image](https://user-images.githubusercontent.com/131929869/236754320-8d5b9513-4556-4055-8c98-ad2b9d749e95.png)

>
 **`Ctrl` + `Alt` + `S`** 동시에 눌러 **Setting** 창를 열고 **Editor > Code Style > File Encodings**를 클릭해주세요.
>
 위 이미지처럼 각 **Encoding** 항목에 **UTF-8**을 선택해주세요.

![image](https://user-images.githubusercontent.com/131929869/236754362-07150ce1-9620-47a1-81e6-a13b6b68aa22.png)

>
 상단 메뉴에 **Help > Edit Custom VM Options...**을 클릭해주세요.

```
-Dfile.encoding=UTF-8
-DConsole.encoding=UTF-8
```

>
 위 코드를 복사하여 열린 파일에 붙여 넣은 후 **IntelliJ를 재기동** 해주세요.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# 참조
- [**WHITEPAEK Tech Docs**](https://whitepaek.tistory.com/41)

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
이상 포스팅을 마치겠습니다.