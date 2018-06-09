# Java学习指南

学习Java的用途：企业服务端开发。

Java学习内容：语法、框架、库、工具。

目录：

- Java语言特性（哪些Java语言特性是Java程序员几乎都必须掌握的）
	- 基础中的基础：基本类型、表达式、流程控制语句
	- 面向对象
	- 泛型
	- Lambda
	- 反射

- Java类库（哪些Java类库是Java服务端程序员几乎都必须掌握的）
	- 核心类库
		- 集合
		- IO/NIO
		- 网络
		- 并发
		- 安全
		- utils
	- 常用第三方类库
		-jdk.management
		- 海量第三方类库

- Java运行机制
	- 解释
	- 编译
	- JIT
	- JVM基础概念和机制
		- 类加载机制
			- Bootstrap
			- Application
			- Extension Class-loader
			- 自定义Class-Loader
		- 垃圾收集基本原理
			- SerialGC
			- Parallel GC
			- CMS
			- G1
			- 适用于什么工作负载
	- 运行时
	- 垃圾收集器
	- 动态编译
	- 辅助功能
		- JFR
	- 服务端运行时

- 工具
	- 编译器
		- javac
		- sjavac
		- jaotc
	- 运行时环境
	- 安全工具
	- 诊断工具
		- jmap
		- jstack
		- jconsole
		- jhsdb
		- jcmd
	- 监控工具
	- 辅助工具
		- jlink
		- jar
		- jdeps
	- 第三方工具
		- AOT
			- GCJ
			- Excelsior JET

- Java生态（什么时候用什么）
	- Java EE
	- Spring
	- Hadoop
	- Spark
	- Cassandra
	- Elastic Search
	- Maven

- Java书籍
	- 《深入理解Java虚拟机》周志明

- Java应用开发
	- SQL数据库编程
	- NoSQL数据编程
	- 主流开源框架
	- 分布式开发

- Java安全
	- 常见的安全问题和处理方法

- Java性能
	- 工具、方法论、实践

## Java运行机制

编译 & 类加载 & JIT & JVM 

分层编译

Hotspot JVM

JVM运行模式
	-Xint 仅解释执行，不编译
	-Xcomp 不解释执行

编译方式
	AOT(Ahead-of-Time Compilation) 直接将字节码编译成机器码

分层编译

JVM语言（合规的字节码都可以在JVM上运行）
	- Clojure
	- Scala
	- Groovy
	- JRuby
	- Jython
	- Kotlin?


## 里程碑

- 掌握java语法

- 用Spring Boot编写web service

	- 读写MySQL

	- 读写Redis

	- loging

	- unit test

	- 读写message queue


## 语法

《Thinking in Java》(Java编程思想)

### 并发

- Runnable: 定义任务的接口
- Thread: 线程，任务在线程中运行
- Executor: 执行者，管理线程
- Callable: 定义带返回值的任务
- 竞争条件：两个或多个任务竞争响应某个条件，因此产生冲突或不一致结果的情况
- 锁
	- synchronized方法
	- Lock对象
	- synchronized(object)临界区
- 原子性：基本类型(long和double必须加volatile)的简单操作（赋值、返回）可视为原子性
- 可视性：如果将一个域声明为volatile，那么只要对这个域产生了写操作，那么所有的读操作就可以看到这个修改
- 原子类（AtomicInteger类等）：提供原子性操作，一般在优化性能时才用到
- 线程本地存储(ThreadLocal类)

## Java关系型数据库编程

- JPA

Java Persistence API是一个用以管理关系数据库数据的Java应用程序接口标准。JPA1.0标准于2006年颁布，最新标准是2017年颁布的JPA2.2标准。

JPA标准文档中指出：JPA的目的是为使用Java领域模型对关系数据库进行管理的Java应用开发者提供对象关系映射（ORM）机制。


JPA有哪些实现：

Hibernate: Hibernate是Java的开源ORM框架，实现了JPA标准。

Spring Data JPA: Spring Data JPA是Spring框架的一部分，提供了一个repository抽象，支持所有可用的JPA实现。

其他：Eclipselink、Toplink等


如何使用JPA：

[JPA Tutorial](https://www.tutorialspoint.com/jpa/index.htm)：一个入门指南，看完基本可以了解JPA的接口是什么样的

Spring Data JPA:

- Repository
- Query Method

The goal of the Spring Data repository abstraction is to significantly reduce the amount of boilerplate code required to implement data access layers for various persistence stores.

technology-agnostic interfaces 


[Accessing data with MySQL](https://spring.io/guides/gs/accessing-data-mysql/)
[Spring Data Commons - Reference Documentation](https://docs.spring.io/spring-data/commons/docs/current/reference/html/)
[Spring Data JPA部分 Reference](https://docs.spring.io/spring-data/jpa/docs/2.0.7.RELEASE/reference/html/#reference)

- JDBC

[JDBC教程(一个快速教程)](https://www.yiibai.com/jdbc/)
[oracle官网jdbc教程](http://www.oracle.com/technetwork/java/javase/jdbc/index.html)

- 连接池

[JDBC实例--JDBC连接池技术解密，连接池对我们不再陌生](https://www.cnblogs.com/liuhongfeng/p/4171785.html)
[Java中三种流行的数据连接池](https://blog.csdn.net/code_du/article/details/24419003)
[JDBC 进阶——连接池](https://www.jianshu.com/p/ad0ff2961597)


- 读写SQL数据库

[spring boot ref文档 Working with SQL Databases](https://docs.spring.io/spring-boot/docs/2.0.1.RELEASE/reference/htmlsingle/#boot-features-sql) 这个文档，仅仅概要地说了下spring boot用了那些技术来访问SQL

[spring data project主页](https://projects.spring.io/spring-data/)

[spring framework ref data access部分](https://docs.spring.io/spring/docs/5.0.5.RELEASE/spring-framework-reference/data-access.html#spring-data-tier)

[Hibernate or JPA or JDBC or?](https://stackoverflow.com/questions/2560500/hibernate-or-jpa-or-jdbc-or?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)

[Hibernate vs JPA vs JDO - pros and cons of each?](https://stackoverflow.com/questions/530215/hibernate-vs-jpa-vs-jdo-pros-and-cons-of-each?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)

[Difference between JPA and JDO?](https://stackoverflow.com/questions/2249841/difference-between-jpa-and-jdo?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)



用orm 

	java中DAO具体指什么

	Java Persistence API (JPA)
		用spring data jpa	
		gnostic(meaning you can use it with Hibernate, Toplink, etc)
		de facto standard

	用hibernate?
		[hibernate官网](http://hibernate.org/)

用jdbc

	Java Database Connectivit

	Spring Framework JDBC abstraction

		在jdbc上做了一层封装，号称使『tedious』的JDBC API变得可以忍受了。

	jdbc 

		[jdbc oracle文档](http://www.oracle.com/technetwork/java/javase/jdbc/index.html)

JDO?
	
	The Java Data Objects (JDO) API is a standard interface-based Java model abstraction of persistence. Application programmers can use JDO technology to directly store Java domain model instances into the persistent store (database)


## 用Spring Boot编写web service

- [github地址](https://github.com/looking4soul/spring-boot-simple)

- 打印hello world的接口

[spring boot ref文档 getting started](https://docs.spring.io/spring-boot/docs/2.0.1.RELEASE/reference/htmlsingle/#getting-started)

## 框架

Spring

- [spring framework project 官方主页](https://projects.spring.io/spring-framework/)
- [spring boot project 官方主页](https://projects.spring.io/spring-boot/)
	- [Spring Boot Samples](https://github.com/spring-projects/spring-boot/tree/v2.0.1.RELEASE/spring-boot-samples)
- 主题
	- 如何在Spring中使用关系型数据库（以MySQL为例）
	- 如何在Spring中使用NoSQL数据库（以Redis为例）
	- 如何在SPring中使用Message Queue（以RabbitMQ为例）


## 库

hibernate

fastjson

gson

Apache HttpClient

Jedis

spring data redis

## 工具

Maven

Gradle

IntelliJ IDEA 

## 源码阅读

spring
spring mvc
tomcat
netty
util
	ArrayList,LinkedList,HashMap,LinkedHashMap,,HashTable,HashSet
	ConcurrentHashMap？
lang
	String,Object,StringBuffer,StringBuilder,Integer
Google guava
junit
okhttp
lucene
elasticsearch

### 如何阅读spring源码

可以先看一下黄勇老师的《架构探险——从零开始写Java Web框架》

了解完Spring架构、模块以及模块对应的功能后，可以针对性阅读部分源码。

推荐《Spring 源码深度解析》，很不错的一本书，目前正在看

github: https://github.com/spring-projects/spring-framework

## 有用的资源

[Java 9 API](https://docs.oracle.com/javase/9/docs/api/overview-summary.html)

## 参考资料

[有哪些 Java 源代码看了后让你收获很多，代码思维和能力有较大的提升？](https://www.zhihu.com/question/61539640)

[怎么阅读Spring源码？](https://www.zhihu.com/question/21346206)

