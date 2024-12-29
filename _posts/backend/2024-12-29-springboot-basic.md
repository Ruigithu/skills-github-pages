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
```java
@WebServlet("/hello")
public class HelloServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        // 1. 获取请求参数
        String name = request.getParameter("name");

        // 2. 处理业务逻辑
        String message = "Hello, " + (name != null ? name : "World");

        // 3. 设置响应内容类型
        response.setContentType("text/html");

        // 4. 渲染视图
        PrintWriter out = response.getWriter();
        out.println("<html><body>");
        out.println("<h1>" + message + "</h1>");
        out.println("</body></html>");
    }
}
```


