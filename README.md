# MyServlet
learn servlet
步骤：
1. idea创建maven-archetype-webapp工程
2. pox.xml增加tomcat7插件和配置tomcat7：run(SomeJava里有配置方式)
3. 增加javax.servlet-api依赖，注意一定要加<scope>provided</scope>，否则与tomcat的jar包冲突会报出下面的log日志
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


servlet的文章：https://www.cnblogs.com/whgk/p/6399262.html  
https://www.cnblogs.com/libingbin/p/5960456.html



严重: Servlet.service() for servlet [jsp] in context with path [] threw exception [java.lang.LinkageError: loader constraint violation: loader (instance of org/apache/jasper/servlet/JasperLoader) previously initiated loading for a different type with name "javax/servlet/http/HttpServletRequest"] with root cause
java.lang.LinkageError: loader constraint violation: loader (instance of org/apache/jasper/servlet/JasperLoader) previously initiated loading for a different type with name "javax/servlet/http/HttpServletRequest"
	at java.lang.Class.getDeclaredMethods0(Native Method)
	at java.lang.Class.privateGetDeclaredMethods(Class.java:2701)
	at java.lang.Class.getDeclaredMethods(Class.java:1975)
	at org.apache.catalina.util.Introspection.getDeclaredMethods(Introspection.java:127)
	at org.apache.catalina.core.DefaultInstanceManager.populateAnnotationsCache(DefaultInstanceManager.java:337)
	at org.apache.catalina.core.DefaultInstanceManager.newInstance(DefaultInstanceManager.java:156)
	at org.apache.catalina.core.DefaultInstanceManager.newInstance(DefaultInstanceManager.java:144)
	at org.apache.jasper.servlet.JspServletWrapper.getServlet(JspServletWrapper.java:172)
	at org.apache.jasper.servlet.JspServletWrapper.service(JspServletWrapper.java:369)
	at org.apache.jasper.servlet.JspServlet.serviceJspFile(JspServlet.java:390)
	at org.apache.jasper.servlet.JspServlet.service(JspServlet.java:334)
	at javax.servlet.http.HttpServlet.service(HttpServlet.java:728)
	at org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:305)
	at org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:210)
	at org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:222)
	at org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:123)
	at org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:472)
	at org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:171)
	at org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:99)
	at org.apache.catalina.valves.AccessLogValve.invoke(AccessLogValve.java:936)
	at org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:118)
	at org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:407)
	at org.apache.coyote.http11.AbstractHttp11Processor.process(AbstractHttp11Processor.java:1004)
	at org.apache.coyote.AbstractProtocol$AbstractConnectionHandler.process(AbstractProtocol.java:589)
	at org.apache.tomcat.util.net.JIoEndpoint$SocketProcessor.run(JIoEndpoint.java:310)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)


### servlet
	[初学 Java Web 开发，请远离各种框架，从 Servlet 开发](https://www.oschina.net/question/12_52027)
