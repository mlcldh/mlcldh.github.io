### 命令行新建Maven项目

#### 方法1

在命令行输入：mvn archetype:generate，会让我们选择项目类型。

默认值是7，maven-archetype-quickstart，是一个普通的Java项目，如果希望使用默认值，直接敲回车即可。

如果希望创建一个web项目，应该输入10，maven-archetype-webapp。

输入groupId、artifactId、version、package。

如果希望version、package使用默认值，直接敲回车即可。

最后输入y表示确认，项目就创建完毕了。

#### 方法2

在命令行输入：

```shell
mvn archetype:generate -DgroupId=com.someOne.some -DartifactId=helloworld -Dversion=1.0.0 -DarchetypeGroupId=org.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart
```

### IDEA新建Maven项目

#### 方法1

新建module，选择Maven，使用archetype。

设置项目信息（项目名称、项目存放路径），最后点击finish。

#### 方法2

不勾选Create from archetype。

设置项目信息（项目名称、项目存放路径），最后点击finish。

设置pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <!-- 模型版本 -->
    <modelVersion>4.0.0</modelVersion>
  <!-- 项目信息 -->
  <groupId>org.mlc</groupId>
  <artifactId>HelloMaven</artifactId>
  <version>1.0.0</version>
  
  <!-- 打包方式 -->
  <packaging>war</packaging>
  
  <!-- 文件编码 -->
  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
  </properties>
  
  <!-- 依赖 -->
  <dependencies>
    <dependy>
      <groupId>javax.servlet</groupId>
      <artifactId>java.servlet-api</artifactId>
      <version>4.0.1</version>
    </dependy>
    <dependy>
      <groupId>javax.servlet</groupId>
      <artifactId>jstl</artifactId>
      <version>1.2</version>
    </dependy>
  </dependencies>
  
  <!-- 构建信息 -->
  <build>
    <!-- 打包后的文件名 -->
    <finalName>helloworld</finalName>
  </build>
  
</project>
```

对项目进行Reimport

打开project Structure，添加web.xml

将web.xml放到src/main/webapp/WEB-INF目录。

