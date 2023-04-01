## Welcome to Apache Tomcat!

### What Is It?

The Apache Tomcat® software is an open source implementation of the Java
Servlet, JavaServer Pages, Java Expression Language and Java WebSocket
technologies. The Java Servlet, JavaServer Pages, Java Expression Language and
Java WebSocket specifications are developed under the
[Java Community Process](https://jcp.org/en/introduction/overview).

The Apache Tomcat software is developed in an open and participatory
environment and released under the
[Apache License version 2](https://www.apache.org/licenses/). The Apache Tomcat
project is intended to be a collaboration of the best-of-breed developers from
around the world. We invite you to participate in this open development
project. To learn more about getting involved,
[click here](https://tomcat.apache.org/getinvolved.html) or keep reading.

Apache Tomcat software powers numerous large-scale, mission-critical web
applications across a diverse range of industries and organizations. Some of
these users and their stories are listed on the
[PoweredBy wiki page](https://cwiki.apache.org/confluence/display/TOMCAT/PoweredBy).

Apache Tomcat, Tomcat, Apache, the Apache feather, and the Apache Tomcat
project logo are trademarks of the Apache Software Foundation.

### Get It

For every major Tomcat version there is one download page containing
links to the latest binary and source code downloads, but also
links for browsing the download directories and archives:
- [Tomcat 10](https://tomcat.apache.org/download-10.cgi)
- [Tomcat 9](https://tomcat.apache.org/download-90.cgi)
- [Tomcat 8](https://tomcat.apache.org/download-80.cgi)
- [Tomcat 7](https://tomcat.apache.org/download-70.cgi)

To facilitate choosing the right major Tomcat version one, we have provided a
[version overview page](https://tomcat.apache.org/whichversion.html).

### Documentation

The documentation available as of the date of this release is
included in the docs webapp which ships with tomcat. You can access that webapp
by starting tomcat and visiting <http://localhost:8080/docs/> in your browser.
The most up-to-date documentation for each version can be found at:
- [Tomcat 10.1](https://tomcat.apache.org/tomcat-10.1-doc/)
- [Tomcat 10.0](https://tomcat.apache.org/tomcat-10.0-doc/)
- [Tomcat 9](https://tomcat.apache.org/tomcat-9.0-doc/)
- [Tomcat 8](https://tomcat.apache.org/tomcat-8.5-doc/)

### Installation

Please see [RUNNING.txt](RUNNING.txt) for more info.

### Licensing

Please see [LICENSE](LICENSE) for more info.

### Support and Mailing List Information

* Free community support is available through the
[tomcat-users](https://tomcat.apache.org/lists.html#tomcat-users) email list and
a dedicated [IRC channel](https://tomcat.apache.org/irc.html) (#tomcat on
Freenode).

* If you want freely available support for running Apache Tomcat, please see the
resources page [here](https://tomcat.apache.org/findhelp.html).

* If you want to be informed about new code releases, bug fixes,
security fixes, general news and information about Apache Tomcat, please
subscribe to the
[tomcat-announce](https://tomcat.apache.org/lists.html#tomcat-announce) email
list.

* If you have a concrete bug report for Apache Tomcat, please see the
instructions for reporting a bug
[here](https://tomcat.apache.org/bugreport.html).

### Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for more info.

### 本地调试
1. 下载 Tomcat 10
2. 添加pom.xml
3. tomcat 依赖 [jakartaee-migration](https://github.com/apache/tomcat-jakartaee-migration) maven 仓没有，需要GitHub 下载本地 mvn install
4. jsp 错误修改
```java
    webConfig();
    context.addServletContainerInitializer(new JasperInitializer(), null);
```
5. JDTCompiler 编译错误修改，注释吊编译错误的行
6. 配置管理员账号信息
```xml
    <user username="admin" password="tomcat" roles="manager-gui"/>
    <user username="robot" password="tomcat" roles="manager-script"/>
    <role rolename="tomcat"/>
    <role rolename="role1"/>
    <user username="tomcat" password="tomcat" roles="tomcat"/>
    <user username="both" password="tomcat" roles="tomcat,role1"/>
    <user username="role1" password="tomcat" roles="role1"/>
    <role rolename="admin-gui"/>
    <role rolename="admin-script"/>
    <role rolename="manager-gui"/>
    <role rolename="manager-script"/>
    <role rolename="manager-jmx"/>
    <role rolename="manager-status"/>
    <user password="tomcat" roles="manager-gui,manager-script,manager-jmx,manager-status,admin-script,admin-gui" username="tomcat"/>
```
7. 调试启动参数配置
```shell
   -Dcatalina.home="E:\code\java\github\tomcat\apache-tomcat-10.1.7\catalina-home"
   -Duser.language=en
   -Duser.region=US
   -Dfile.encoding=UTF-8
   -Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager
   -Djava.util.logging.config.file=E:\code\java\github\tomcat\apache-tomcat-10.1.7\catalina-home\conf\logging.properties
```
