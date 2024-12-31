![image](https://github.com/user-attachments/assets/ba90c374-cde8-4748-8564-6aad9ea81712)

1.逻辑视图:从终端用户角度看系统提供给用户的功能，对应 UML 的 `class` 和 `state diagrams`。

2.处理视图:从动态的角度看系统的处理过程，对应 UML 的 `sequence` 和 `activity diagrams`。

3.开发视图:从程序员角度看系统的逻辑组成，对应 UML 的 `package diagrams`。

4.物理视图:从系统工程师角度看系统的物理组成，对应 UML 的 `deployment diagrams`。

5.场景视图:从用户角度看系统需要实现的需求，对应 UML 的 `use case diagrams`。
![image](https://github.com/user-attachments/assets/17b8fcfb-fe76-4ab0-9c83-1b2339b7a44a)

第一步：明确 Rank:不要事无巨细地把一个大系统的方方面面都在一张架构图中展现出来，而应该明确你要阐述的系统所属的级别（L0～L4），然后只描述这个级别的架构信息。

第二步：画出 Role:从不同的角度来分解系统，看看系统包含哪些角色。角色对应架构图中的区块、图标和节点等。

第三步：画出 Relation:有了角色后，画出角色之间的关系，对应架构图中角色之间的连接线。不同的连接线可以代表不同的关系。

第四步：最后画出 Rule:挑选核心场景，画出系统角色之间如何协作来完成某项具体的业务功能，对应系统序列图。
![image](https://github.com/user-attachments/assets/91138845-45c2-4f93-865a-be541f8508ac)

刚才介绍4+1视图的时候，我提到过，从不同的角度去剖析系统，就会得到不同的视图。其实按照4R架构定义来画架构图也是这样，用不同的方式去划分系统，就会得到不同类型的架构，分别对应不同类型的架构图。常见的类型整理如下

![image](https://github.com/user-attachments/assets/136e12e7-60f0-4fd4-916b-d37f1587a559)
1. 业务架构图

   【定义】
   描述系统对用户提供了什么业务功能，类似于 4+1 视图的场景视图。
   
   【使用场景】

   1.产品人员规划业务：比如说我们经常在产品规划和汇报会议上看到产品人员会用业务架构图来展现业务全局状态。

   2.给高 P 汇报业务：对于P7+以上级别的技术人员，在汇报的时候不能光讲技术，也要讲业务的发展情况，用业务架构图就比较容易的展现业务整体情况。

   3.给新员工培训业务。

![image](https://github.com/user-attachments/assets/94a451e0-fcf8-4e28-9b3b-ac9fda9bde7f)

这张业务架构图有三点关键信息：
“MTR”区块是浅红色的，“人传人”区块是绿色的，浅红色代表正在进行的，绿色代表明年规划的。
分了4组：钱包业务、第三方业务、商家服务和用户管理。
“转账”和“社交红包”等区块比较长，只是为了对齐后更美观，不代表业务本身的量级或者重要程度，如果要表示这样的信息，那么可以用颜色来表示。

2. 客户端和前端架构图

   【定义】
   描述客户端和前端的领域逻辑架构，关注的是从逻辑的角度如何分解客户端或者前端应用。

   【使用场景】

   1.整体架构设计：由客户端或者前端架构师完成本领域的架构设计。

   2.架构培训。

   【参考案例】
   
   微信客户端架构3.x的架构图如下所示：
![image](https://github.com/user-attachments/assets/bafa332b-2c4f-41e7-85f0-4a4d4865af0c)

  1.图中用了灰色（app:UI等）、蓝色（Net Scene等）、深灰色（Storage）、浅蓝色（Network）来表示不同类型的模块。

  2.图中有两类连接线：双向的（WebViewUI和app:UI），单向的（app:UI和Net Scene等）。

  3.整体上分为4组，对应图中背景色不同的四个大的区块。

3. 系统架构图

   【定义】

   描述后端的逻辑架构，又叫“后端架构”或“技术架构”，不管是业务系统、中间件系统，还是基础的操作系统、数据库系统等，系统架构都是软件系统架构的核心。

   【使用场景】

   1.整体架构设计。

   2.架构培训。

   【参考案例】

   如果系统比较简单，可以参考MongoDB Sharding的系统架构图，如下所示：

![image](https://github.com/user-attachments/assets/3956348e-3ae0-4f5e-915f-e6b5ac110143)

如果系统相对复杂，建议首先用一张图来展示系统架构里面的角色（Role）以及每个角色的核心功能；然后再用一张图来展示角色之间的关系（Relation），可以参考一个支付中台的系统架构图，如下所示：

![image](https://github.com/user-attachments/assets/d5de2437-3ad9-4333-a947-cadf13060f5c)

![image](https://github.com/user-attachments/assets/2f768fd3-bcdc-483b-acbb-3867d159204d)

4. 应用架构图

   【定义】
   描述后端系统由哪些应用组成，一个应用就是一个可部署发布运行的程序，它是项目开发过程中，开发测试运维团队协作的基础。

   【使用场景】

   1.项目开发、测试。

   2.运维部署发布。

   3.子域架构设计。

   【参考案例】
   如果系统比较简单，那么基本上应用架构和系统架构是等价的，可以参考MongoDB Sharding的应用架构图，如下所示：
![image](https://github.com/user-attachments/assets/ec31d8a7-da72-4085-847a-a588a7e6c657)

这张图中的Router（mongos）、Config Servers 和 Shard（replica set），既包含了系统架构的角色信息（Router、Config Servers 和 Shard），又包含了应用信息（mongos、Config Servers 和 Shard）。
如果系统比较复杂，按照架构分层的角度来看，应用架构已经到了可执行程序这一层，例如支付中台这一类的系统，包含的应用可能有几百上千个，如果把整个支付中台所有的应用都在一张图里面展示出来，信息太多太密，可能会导致架构图都看不清。
这种情况下，应用架构一般都是按照子域来画应用架构图，可以参考支付中台的会员域的应用架构图，如下所示：
![image](https://github.com/user-attachments/assets/8ab5578d-b94a-42c0-afff-1e80d71a4e89)

5. 部署架构图

   【定义】
   描述后端系统具体是如何部署的，主要包含机房信息、网络信息和硬件信息等。

   【使用场景】

   1.总体架构设计。

   2.运维规划和优化。

   【参考案例】
   一个简单的支付系统的部署架构图如下所示：
![image](https://github.com/user-attachments/assets/ce4cf1c4-1cdc-413f-ba31-5e475bdcfabf)

8. 系统序列图

   【定义】

   描述某个业务场景下，系统各个角色如何配合起来完成业务功能。

   【使用场景】

   结合“系统架构、应用架构和部署架构”来使用。

   【参考案例】

   扫码支付这个支付核心场景的系统序列图如下所示：
   
![image](https://github.com/user-attachments/assets/6dac6b88-a346-40be-b57e-b924e8da8809)

总结 

![image](https://github.com/user-attachments/assets/a009701c-f5c0-4df4-837a-6ab495ab62c4)
