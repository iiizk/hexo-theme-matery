---
title: jdk_install
date: 2022-04-13 20:34:46
tags:
---
## jdk-8u181：
`https://www.aliyundrive.com/s/9tyyKJm6mwv`


### path环境
### JAVA_HOME 
`C:\Program Files\Java\jdk1.8.0_181`
![jdk0](/images/jdk/jdk0.png)
### CLASSPATH
`.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar`
![jdk1](/images/jdk/jdk1.png)




### （推荐移动到最上面）如果有其他的jdk环境就移动到最上面
### path中设置
`%JAVA_HOME%\bin`
`%JAVA_HOME%\jre\bin`
![jdk2](/images/jdk/jdk2.png)


```如果path变成横着的我们需要在前面加一个C:\Windows\System32;```
![jdk3](/images/jdk/jdk3.png)
### 若在安装JDK时安装了JRE，则可以不在Path中配置JRE的环境变量，若冲突，则去掉JRE的环境变量

### 检查
```
javac
java
java -version
javac -version
```
![jdk4](/images/jdk/jdk4.png)