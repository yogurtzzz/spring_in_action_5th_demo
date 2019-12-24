Spring Boot DevTools

It provide developers with some handy tools during  development time

- Automatic application restart when code change
- Automatic browser refresh when browser-destined resources change（css / js / images / templates）
- Automatic disable of template caches
- Build-in H2 DB Console with H2 presence



**1.Automatic restart when code change**

When DevTools is in play.**The application is loaded into 2 separate class loaders in JVM**. One loader is loaded with your own java code,which are likely to change frequently.

The other loader is loaded with dependency libraries ,which aren't likely to change as often.

When a change is detected, DevTools only reload the loader containing your project code and restart Spring Application Context.

But when you add , remove a dependency . the other class loader containing dependency libraries isn't automatic reloaded.



**2.Automatic browser refresh and template cache disable**

template engine like Thymeleaf are configured to cache the results of template parsing so that templates don't need to be reparsed with every request. This can bring some performance improvement in production. But are not so good at development time. Cause we need to see the results when changes are made to templates and refresh the browser.

**DevTools addresses this issue by automatically disabling all template caching.**

Make as many changes as you want to your templates and know that you’re only a browser refresh away from seeing the results.

But with the **LiveReload** server that DevTools automatically enables with your application, you don't even bother to click the browser's refresh button to see the results. Note that you need to install **LiveReload browser plugin** to make this happen.  The plugin are available with Google Chrome ,FireFox, and Safari. See  http://livereload.com/extensions/ 





--------------------------

That’s an important benefit of developing with Spring. You can focus on the code that meets the requirements of an application rather than on satisfying the demands of a framework. Spring (with Spring Boot) can be considered the frameworkless framework







Survey the Spring landscape

**1.The core Spring Framework**

It's the foundation of everything else in Spring universe. It provides core container and dependency injection. And other essential feature like Spring MVC, Spring's web framework , basic data persistence support , like `JdbcTemplate`

In Sprint 5.0.8. support was added for reactive-style programming, including a new reactive web framework called **Spring WebFlux**, which borrows a lot from Spring MVC

**2.Spring Boot**

In addition to starter dependencies and autoconfiguration , Spring Boot also offers some other useful features.

- **Actuator** : provide runtime insight into inner working of an application , including metrics , thread dump info , application health , environment properties 

**3.Spring Data**

the ability to define your application’s data repositories as simple Java interfaces, using a naming convention when defining methods to drive how data is stored and retrieved.

Besides, Spring Data can work well with several different kinds of databases, including relational（JPA），document（Mongo），graph（Neo4J） and others

**4.Spring Security**

Spring Security addresses a broad range of application security needs, including authentication, authorization, and API security.



**5.Spring Cloud**

a collection of projects for developing cloud-native applications with Spring