# MyServlet
learn servlet
步骤：
1. idea创建maven-archetype-webapp工程
2. pox.xml增加tomcat7插件和配置tomcat7：run(SomeJava里有配置方式)
3. 增加javax.servlet-api依赖，注意一定要加<scope>provided</scope>，否则与tomcat的jar包冲突
4. 编写MyServlet代码
5. 配置web.xml
```
<web-app>
  <display-name>Archetype Created Web Application</display-name>
  <servlet>
    <servlet-name>myservlet</servlet-name>
    <servlet-class>com.demo.MyServlet</servlet-class>
  </servlet>
  <servlet-mapping>
    <servlet-name>myservlet</servlet-name>
    <url-pattern>/*</url-pattern>
  </servlet-mapping>
</web-app>
```
6. 运行
