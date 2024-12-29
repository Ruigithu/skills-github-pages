---
layout: post
title: Spring Boot Basic
date: 2024-12-29
category: springboot
tags: [java, spring, web]
---
 
# Basic Springboot
## Servlet->Spring->Springboot
### Servlet
>Servlet 是一种用于扩展服务器功能的 Java 类，特别是在 Web 应用程序中处理客户端请求和响应的技术。它通常运行在支持 Java 的 Web 服务器或应用服务器中（如 Apache Tomcat、Jetty 等），并能够处理 HTTP 请求。
+ 编写一个普通类extends the HttpServlet 类
+ (可以通过注解@WebServlet来避免在xml文件中配置url)
```java
public class HelloServlet extends HttpServlet {
    //由于get或post只是请求的不同方式，所以可以相互调用，因为业务逻辑相通
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        PrintWriter writer = resp.getWriter();
        writer.print("Hello,World!");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        super.doPost(req, resp);
    }
}
```
+ 缺点：自己配置
## Spring


