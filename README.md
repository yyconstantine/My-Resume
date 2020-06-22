<center><font size=5><strong>宋xx</strong></font></center><br/>

<center>yyconstantine@gmail.com | 北京</center><br/>

<center>个人博客：https://yyconstantine.github.io</center><br/>

<center>求职意向：Java开发 | 工作年限：2年</center>

#### **<font color=#0099ff size=3>教育经历</font>**
---
> 2014.09&nbsp;-&nbsp;2018.07&nbsp;|&nbsp;太原理工大学&nbsp;|&nbsp;本科&nbsp;|&nbsp;应用化学
- 主修四大化学、高等数学等理工课程，有良好的理工思维习惯
- 辅修数据结构、Java程序设计、操作系统、网络原理等课程，在校期间参加第三届"互联网+"比赛，独立负责微信小程序的开发

#### **<font color=#0099ff size=3>专业技能</font>**
---
- 编程语言：熟悉面向对象编程思想、Java基础，熟悉多线程如juc包，熟悉常用设计模式如代理、门面、策略模式，了解常见数据结构及算法
- 框架：熟悉SpringBoot、SSM，熟悉Dubbo、SpringCloud，熟悉主流web容器如tomcat、WebLogic，熟悉RestFul规范，熟悉常见中间件如Redis、RocketMQ、Zookeeper
- 数据库：熟悉MySQL、Oracle，熟练掌握常用sql语句编写，熟悉sql语句的性能优化
- 操作系统：熟练切换在Linux、OS X、Windows下的开发
- 辅助技能：熟悉Git、SVN等版本管理工具，Maven等项目管理工具，熟悉敏捷工具如Jira，熟悉敏捷开发模式

#### **<font color=#0099ff size=3>工作经验</font>**
---
> 2019.05&nbsp;-&nbsp;至今&nbsp;|北京xx有限公司（100-499人）|&nbsp;Java开发工程师
```
项目名称：和卡生活
开发环境：idea + SVN + Oracle11g2 + JDK8
技术栈：SpringBoot + MyBatis + Dubbo + Zookeeper + RocketMQ + Redis + Tomcat + Quartz
```

- 项目为半径生活的拓展模式，以小程序为载体，以线上/线下购卡，线下支付模式的跨行业储值卡业务
- 项目使用SpringBoot搭建服务，使用Dubbo作为服务治理框架，Zookeeper为注册中心，Redis作为缓存处理，RocketMQ处理异步业务
- 个人工作：
  - 负责项目框架的搭建，Maven的依赖管理
  - 参与服务划分：以业务为维度进行拆分，并对个别重要业务进行细分，预计迭代较多的服务单独划分
  - 网关搭建：网关层实现出入参非对称加密及api路由、集群部署和负载均衡，Redis做配置中心
  - 分布式事务：分布式事务主要服务于交易模块，由于涉及到订单服务、卡交易服务，利用RocketMQ进行消息补偿实现了事务的**最终一致性**
  - 接口幂等：对需要实现幂等的接口以获取token（或称版本号）形式做接口幂等验证
  - 业务编写：负责核心业务如卡交易的编写，搭建RocketMQ环境并实现普通消息和事务消息的发送及消费
  - 代码规范：推荐使用JDK8新特性，使用Alibaba Code Guide + FindBugs进行代码扫描，在完成业务的基础上合理优化和重构代码

```
项目名称：聚合支付
开发环境：idea + SVN + Oracle11g2 + JDK7 + Windows10
技术栈：Spring + SpringMVC + Hibernate + JPA + Redis + WebLogic
```

- 项目为集成银联网联、微信支付、支付宝支付等多种支付通道实现“一码多付”及“多码一扫”的聚合支付业务
- 个人工作：
    - 单笔交易查询优化：由于部分接入的商户是通过其他厂商的pos机对接的支付接口，其中部分pos机在交易发起后会直接进行发起**轮询查询**订单支付状态。交易高峰时响应相对缓慢，大量商户的pos同时发起交易查询全部打到数据库导致数据库宕机。通过实际调研，确认了商户在支付时所需的订单热点数据，对其大小计算并推算日最高交易量，将全部完成的订单进行缓存，防止大量查询请求打崩数据库
    - 交易查询报表优化：由于交易订单表未进行分库分表或归档，业务规模膨胀后表内数据迅速上升（优化时单表有亿级数据），导致后台报表查询过于缓存，即使走索引效果也并不理想（运营需求是查询近一个月的交易数据，一次性load数据量过多，导致速度缓慢）。最终采用CountDownLatch对查询日期进行切割，分成每次load较少数据量，等待全部查询线程返回后，主线程进行组装，提升了一定查询性能（6min -> 2min）

> 2018.07&nbsp;-&nbsp;2019.03&nbsp;|&nbsp;京东（10000人以上）&nbsp;|&nbsp;系统运维工程师
- 参与对内办公软件（IM类）的产品迭代，参与产品设计，跟进产品开发全流程，参与敏捷开发
- 基于用户工单和产品场景进行业务模式的设计，转化可用的用户需求，跟进开发的流程及产品落地后的用户体验，深入理解产品的业务模式
- 完善业务运维的文档库，保证了组内人员的业务互通、相互备份

#### **<font color=#0099ff size=3>项目经验</font>**
---
> 项目地址：[https://github.com/yyconstantine/Dubbo-Generic-GateWay](https://github.com/yyconstantine/Dubbo-Generic-GateWay)
```
项目名称：网关服务
开发环境：IDEA + Maven + Git + JDK8 + OS X
技术栈：SpringBoot + Zookeeper + Redis + Nacos + Dubbo
```
- 项目介绍：dubbo网关，对外暴露http接口，自定义rpc接口暴露方式，支持多种配置中心，自动感知接口变更，支持SPI注册自定义接口配置方式
- 功能描述：
  - 通过自定义注解+包扫描的方式达到rpc接口级的配置方式（路由属性、dubbo-provider属性）
  - 项目初始化时自动扫描依赖网关jar包的服务并自动上报接口信息，基于Dubbo SPI的方式支持多种配置方式及用户自定义配置
  - 基于配置中心（如Zookeeper、Nacos）的监听机制实现接口变更动态感知，毫秒级同步
  - 使用Dubbo泛化调用的方式进行http到rpc的协议转换
---
> 项目地址：https://yyconstantine.github.io
- 个人日常学习博客，包括工作遇到问题的总结及新技术的学习


**<font color=#0099ff size=3>技能证书</font>**

---
> 2015
- CET-6

**<font color=#0099ff size=3>自我评价</font>**

---

- 自我驱动，兴趣驱动，纯自学入行，非培训，看过网课不算：）
- 开发经验不多，但自我评价成长较快，愿意以热情的态度吸收、学习新知识，拥抱开源，愿意实践更加合理有效的规范
- 拥簇合理的研发流程，会在业余主动进行代码重构、优化，有代码洁癖
