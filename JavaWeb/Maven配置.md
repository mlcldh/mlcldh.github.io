## 概述

[Apache Maven](https://maven.apache.org/)主要用于自动化构建和管理Java项目。

基于项目对象模型（POM，Project Object Model）的概念。

下载apache-maven-3.6.3-bin.zip，下载地址：[https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi)

## 配置

### 配置MAVEN_HOME

必须配置好JAVA_HOME，Maven对JDK版本的要求：[http://maven.apache.org/docs/history.html](http://maven.apache.org/docs/history.html)

添加MAVEN_HOME/bin到PATH中。这里只讲在Mac上的配置。

1、终端执行

```shell
vim ~/.bash_profile
```

2、按下i进入编辑模型，添加

```shell
export MAVEN_HOME=/usr/local/apache-maven-3.6.3
export PATH=$PATH:$MAVEN_HOME/bin
```

3、按ESC退出编辑模型，保存并退出

```shell
:wq
```

4、在终端输入以下命令使`bash_profile`生效

```shell
source ~/.bash_profile
```

5、验证是否成功

```shell
mvn -v
```

Apache Maven 3.6.3，能看到版本信息即表示成功。

### 修改仓库位置

在%MAVEN_HOME%/conf/settings.xml的<settings>标签中添加<localRepository>

```xml
<localRepository>YourCustomPath/.m2/repository</localRepository>
```

## 源配置

为提高仓库的下载速度，在%MAVEN_HOME%/conf/settings.xml的<mirrors>标签中添加<mirror>

```xml
<mirror>
  <id>aliyun</id>
  <name>aliyun</name>
  <url>https://maven.aliyun.com/repository/public</url>
  <mirror>central</mirror>
</mirror>
```

### 修改Maven项目的JDK版本

#### 方法1

在pom.xml中添加属性（每个Maven项目都要添加）

```xml
<properties>
  <maven.compiler.source>8</maven.compiler.source>
  <maven.compiler.target>8</maven.compiler.target>
  <maven.compiler.compilerVersion>8</maven.compiler.compilerVersion>
</properties>
```

#### 方法2

在pom.xml中添加插件（每个Maven项目都要添加）

```xml
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-compiler-plugin</artifactId>
  <version>3.8.1</version>
  <configuration>
    <source>8</source>
    <target>8</target>
  </configuration>
</plugin>
```

#### 方法3

在%MAVEN_HOME%/conf/settings.xml的<profiles>标签中添加<profile>

这是一种一劳永逸的办法，不需要去修改每一个Maven项目的pom.xml

```xml
<profile>
  <id>jdk8</id>
  <activation>
    <activeByDefault>true</activeByDefault>
    <jdk>8</jdk>
  </activation>
  <properties>
    <maven.compiler.source>8</maven.compiler.source>
    <maven.compiler.target>8</maven.compiler.target>
    <maven.compiler.compilerVersion>8</maven.compiler.compilerVersion>
  </properties>
</profile>
```

