# **`Zero-One-10wms`**

Reference for the concept of `WMS`:

- https://en.wikipedia.org/wiki/Warehouse_management_system
- https://baike.baidu.com/item/%E4%BB%93%E5%BA%93%E7%AE%A1%E7%90%86/9163356


## **Project Overview**

A Warehouse Management System (`WMS`) is a software solution that provides visibility into an enterprise's entire inventory and manages fulfillment operations across the supply chain, from distribution centers to store shelves. By coordinating and optimizing resource utilization and material flow, it helps businesses maximize labor, space, and invested equipment. It is designed to meet the demands of the entire global supply chain, including distribution, manufacturing, asset-intensive, and service-based businesses.

In today's dynamic, omnichannel fulfillment economy, online consumers expect to purchase, fulfill orders, and return products anytime and anywhere. This requires businesses to use appropriate warehouse management software to enhance fulfillment capabilities and quickly respond to customer demands.

`zero-one-10wms` is designed to help you meet the future needs of the supply chain by aligning inventory management and fulfillment services with modern purchasing methods. It provides real-time visibility into your entire inventory. As long as there is internet access, users can track inventory in real time via smartphones and browsers.


## **System Architecture**

The project is built on the `Spring Cloud Alibaba` ecosystem, utilizing `MySQL` for data persistence, and the front end is developed with the `Vue3` ecosystem and `Element Plus UI` framework. The project also supports `C++` microservice development and integration while using `Jenkins` for `CD/CI`.

![architecture](./documents/00、preview-pic/architecture.jpg)


## **Project Structure**

> `zero-one-10wms`
>
> > `.gitignore` -- Git ignore file
> >
> > `README.md` -- Project README file
> >
> > `documents` -- Documentation resources (environment setup, coding standards, project requirements, etc.)
> >
> > `wms-java` -- Main Java project
> >
> > `wms-cpp` -- Main C++ project
> >
> > `wms-frontend` -- Main frontend project


## **Software Architecture**

### **Java Tech Stack**

#### **Core Backend Tech Stack**

Version compatibility reference:

https://github.com/alibaba/spring-cloud-alibaba/wiki/%E7%89%88%E6%9C%AC%E8%AF%B4%E6%98%8E

| Technology               | Description                 | Version         | Notes |
|--------------------------|----------------------------|----------------|-------|
| `Spring`                 | Container                   | 5.2.15         | [Spring](https://spring.io/) |
| `Spring Web MVC`         | MVC framework              | 5.2.15         | [Spring Web MVC](https://docs.spring.io/spring/docs/current/spring-framework-reference/web.html) |
| `Beanvalidation`         | Entity attribute validation | 2.0.2          | [Beanvalidation](https://beanvalidation.org/2.0-jsr380/) |
| `MyBatis`                | ORM framework              | 3.5.7          | [MyBatis](http://www.mybatis.org/mybatis-3/zh/index.html) |
| `MyBatis Plus`           | MyBatis enhancement tool    | 3.4.3.4        | [MyBatis Plus](https://baomidou.com/) |
| `MyBatis Plus Generator` | Code generator             | 3.5.1          | [MyBatis Plus Generator](https://github.com/baomidou/generator) |
| `Druid`                  | Database connection pool   | 1.2.8          | [Druid](https://github.com/alibaba/druid) |
| `Lombok`                 | Java entity helper tool    | 1.18.20        | [Lombok](https://github.com/rzwitserloot/lombok) |
| `Hutool`                 | Java utility library       | 5.8.3          | [Hutool](https://hutool.cn/docs/#/) |
| `Knife4j`                | API documentation tool     | 2.0.8          | [Knife4j](https://gitee.com/xiaoym/knife4j) |
| `Nimbus JOSE JWT`        | JSON Web Token (JWT)       | 8.21           | [Nimbus JWT](https://bitbucket.org/connect2id/nimbus-jose-jwt/wiki/Home) |
| `Spring Boot`            | Spring Boot framework      | 2.3.12         | [Spring Boot](https://spring.io/projects/spring-boot) |
| `Spring Cloud`           | Microservices framework    | `Hoxton.SR12`  | [Spring Cloud](https://spring.io/projects/spring-cloud) |
| `Spring Cloud Alibaba`   | Alibaba microservices tools | 2.2.8         | [Spring Cloud Alibaba](https://github.com/alibaba/spring-cloud-alibaba/wiki) |
| `Spring Cloud Security`  | Authentication & Authorization | 2.2.5      | [Spring Cloud Security](https://spring.io/projects/spring-cloud-security) |
| `Sentinel`               | Distributed system protection | 1.8.4        | [Sentinel](https://sentinelguard.io/zh-cn/) |
| `Seata`                  | Distributed transaction solution | 1.5.1    | [Seata](https://seata.io/zh-cn/) |
| `MapStruct`              | Code generator for entity mapping | `1.5.3.Final` | [MapStruct](https://mapstruct.org/) |

#### **Extended Backend Tech Stack**  

| Technology                | Description               | Version | Notes |
|---------------------------|--------------------------|---------|-------|
| `EasyExcel`               | Excel report tool        | 3.0.5   | [EasyExcel](https://github.com/alibaba/easyexcel) |
| `RocketMQ`                | Message queue middleware | 4.9.3   | [RocketMQ](https://github.com/alibaba/spring-cloud-alibaba/wiki/RocketMQ) |
| `WebSocket`               | Real-time communication  | 5.2.15  | [WebSocket](https://docs.spring.io/spring-framework/docs/5.3.15/reference/html/web.html#websocket) |
| `FastDFS`                 | Distributed file system  | 2.0.1   | [FastDFS](https://gitee.com/zero-awei/fastdfs-spring-boot-starter) |
| `Elasticsearch`           | Distributed search engine | 7.6.2  | [Elasticsearch](https://www.elastic.co/guide/en/elasticsearch/reference/7.6/index.html) |
| `LogStash`                | Log collection tool      | 7.6.2   | [LogStash](https://www.elastic.co/guide/en/logstash/7.6/index.html) |
| `Kibana`                  | Log visualization tool   | 7.6.2   | [Kibana](https://www.elastic.co/guide/en/kibana/7.6/index.html) |
| `logstash-logback-encoder` | Logstash log collection plugin | 6.6 | [Logstash Logback Encoder](https://github.com/logfellow/logstash-logback-encoder/tree/logstash-logback-encoder-6.6) |
| `spring-boot-admin`       | Service monitoring panel | 2.3.1   | [Spring Boot Admin](https://github.com/codecentric/spring-boot-admin) |
| `EasyEs`                  | Elasticsearch ORM framework | 1.0.3  | [EasyEs](https://www.easy-es.cn/) |
| `spring-data-mongodb`     | Spring MongoDB integration | 3.0.9  | [Spring Data MongoDB](https://docs.spring.io/spring-data/mongodb/docs/3.0.9.RELEASE/reference/html/#preface) |
| `AJ-Captcha`              | Captcha plugin          | 1.3.0   | [AJ-Captcha](https://ajcaptcha.beliefteam.cn/captcha-doc/) |
| `x-easypdf`               | PDF plugin              | 2.12.2  | [x-easypdf](https://gitee.com/dromara/x-easypdf) |


### `Frontend` Tech Stack

#### Core Tech Stack

| Technology     | Description             | Version  | Notes |
|---------------|-------------------------|----------|-------|
| `Vue`         | Frontend framework       | `v3.x`   | [Vue.js](https://v3.vuejs.org/) |
| `Vue-Router`  | Routing framework        | `v4.x`   | [Vue Router](https://next.router.vuejs.org/) |
| `Pinia`       | Global state management  | `v2.x`   | [Pinia](https://pinia.vuejs.org/) |
| `Axios`       | HTTP middleware          | v1.7.2   | [Axios](https://github.com/axios/axios) |
| `Element-Plus` | UI framework             | `latest` | [Element Plus](https://element-plus.gitee.io/zh-CN/) |

#### **Extended Tech Stack**  

| Technology              | Description         | Version  | Notes |
|-------------------------|---------------------|----------|-------|
| `ECharts`               | Charting framework  | `latest` | [ECharts](https://echarts.apache.org/handbook/zh/get-started/) |
| `AJ-Captcha`            | Captcha plugin     | 1.3.0    | [AJ-Captcha](https://ajcaptcha.beliefteam.cn/captcha-doc/) |
| `SheetJS`               | Spreadsheet plugin  | 0.20.2   | [SheetJS](https://docs.sheetjs.com/docs/) |
| `vue-plugin-hiprint`    | Printing plugin     | 0.0.56   | [Hiprint](https://gitee.com/CcSimple/vue-plugin-hiprint) |
| `wangEditor`            | Rich text editor    | v5       | [wangEditor](https://www.wangeditor.com/v5/) |
| `pdfobject`             | PDF preview plugin  | 2.3.0    | [PDFObject](https://github.com/pipwerks/PDFObject) |
| `Vitest`                | Testing framework   | 1.6.0    | [Vitest](https://cn.vitest.dev/) |


### `C++` Tech Stack

#### Core Backend Tech Stack

| Technology | Description | Version | Notes |
|------------|------------|---------|-------|
| `oat++` | Web framework | `1.3.0` | https://github.com/oatpp/oatpp |
| `MySQL Connector` | MySQL connection driver | 8.0.27 | https://dev.mysql.com/doc/connector-cpp/1.1/en/connector-cpp-apps.html |
| `JWT` | JSON Web Token | v1.4 | https://opensourcelibs.com/lib/cpp-jwt |
| `OpenSSL` | Open-source security protocol | `1.1.1L` | https://www.openssl.org/ |

#### **Extended Backend Tech Stack**  

| Technology   | Description                | Version  | Notes |
|-------------|----------------------------|----------|-------|
| `xlnt`      | Excel report tool          | 1.5.0    | [xlnt](https://github.com/tfussell/xlnt) |
| `fastdfs`   | File storage client        | latest   | [FastDFS](https://gitee.com/fastdfs100) |
| `yaml-cpp`  | YAML data parser           | 0.7.0    | [yaml-cpp](https://github.com/jbeder/yaml-cpp) |
| `nacos`     | Nacos client               | `v1.1.0` | [Nacos SDK C++](https://github.com/nacos-group/nacos-sdk-cpp) |
| `redis++`   | Redis connection client    | 1.3.2    | [redis-plus-plus](https://github.com/sewenew/redis-plus-plus) |
| `rocketmq`  | RocketMQ client            | 2.1.0    | [RocketMQ C++](https://github.com/apache/rocketmq-client-cpp) |
| `mongo`     | MongoDB client             | 3.6.5    | [MongoDB C++ Driver](https://www.mongodb.com/docs/drivers/cxx/) |
| `libharu`   | PDF library                | 2.4.3    | [libharu](https://github.com/libharu/libharu/tree/v2.4.3) |
| `zxing`     | Barcode & QR code generator | 2.1.0    | [zxing-cpp](https://github.com/zxing-cpp/zxing-cpp/tree/v2.1.0) |



## Environment Requirements

### Development Tools

| Tool           | Description                | Version    | Notes |
|---------------|----------------------------|------------|-------|
| `Navicat`     | Database connection tool   | latest     | [Navicat](https://www.navicat.com.cn/) |
| `RDM`         | Redis visualization tool   | latest     | [RedisDesktopManager](https://github.com/uglide/RedisDesktopManager) / [AnotherRedisDesktopManager](https://gitee.com/qishibo/AnotherRedisDesktopManager) |
| `PowerDesigner` | Database design tool     | 16.6       | [PowerDesigner](http://powerdesigner.de/) |
| `Axure`       | Prototype design tool      | 9          | [Axure](https://www.axure.com/) |
| `MindMaster`  | Mind mapping tool          | latest     | [MindMaster](http://www.edrawsoft.cn/mindmaster) |
| `Visio`       | Flowchart tool             | latest     | [Visio](https://www.microsoft.com/zh-cn/microsoft-365/visio/flowchart-software) |
| `Apipost`     | API debugging tool         | latest     | [Apipost](https://www.apipost.cn/) |
| `Mock.js`     | API mock testing           | latest     | [Mock.js](http://mockjs.com/) |
| `Git`         | Version control            | latest     | [Git](https://git-scm.com/) |
| `Codeup`      | Source code hosting        | latest     | [Codeup](https://codeup.aliyun.com) |
| `Projex`      | DevOps process management  | latest     | [Projex](https://devops.aliyun.com/projex) |
| `IDEA`        | Java IDE                   | 2022.1.3+  | [IntelliJ IDEA](https://www.jetbrains.com/idea/download) |
| `Apache Maven` | Build tool                | 3.6.3      | [Maven](https://maven.apache.org/) |
| `Docker Maven` | Maven Docker plugin      | 0.40.2     | [Docker Maven Plugin](https://dmp.fabric8.io/) |
| `VS`          | C++ IDE                    | 2022       | [Visual Studio](https://learn.microsoft.com/en-us/visualstudio/releases/2022/release-notes) |
| `Cmake`       | C++ cross-platform build   | latest     | [CMake](https://cmake.org/cmake/help/latest/index.html) |
| `gtest`       | C++ testing framework      | 1.14.0     | [Google Test](https://github.com/google/googletest) |
| `VS Code`     | Frontend development IDE   | latest     | [VS Code](https://code.visualstudio.com/Download) |


### Development Environment

| Dependency | Version | Notes |
|-----------|---------|-------|
| `Windows` | 10+ | Operating system |
| `JDK` | 1.8.0_191+ | https://www.injdk.cn/ |
| `NodeJS` | 20.15.0 | https://nodejs.org/zh-cn/ |
| `NPM` | 8.19.2 | https://www.npmjs.com/ |


### Server Environment

| Dependency   | Version   | Notes |
|-------------|----------|-------|
| `Anolis OS` | `8.6GA`  | [Anolis OS](https://openanolis.cn/anolisos) |
| `Docker`    | latest   | [Docker](https://www.docker.com/) |
| `MySQL`     | 8.0.20   | [MySQL](https://www.mysql.com/cn/) |
| `Redis`     | 6.2.7    | [Redis](https://redis.io/) |
| `Nacos`     | 2.1.0    | [Nacos](https://nacos.io/zh-cn/docs/quick-start-docker.html) |
| `Sentinel`  | 1.8.4    | [Sentinel](https://github.com/alibaba/Sentinel/releases) |
| `Seata`     | 1.5.1    | [Seata](https://github.com/seata/seata) |
| `RocketMQ`  | 4.9.3    | [RocketMQ](https://rocketmq.apache.org/) |
| `Nginx`     | latest   | [Nginx](https://nginx.org/en/) |
| `FastDFS`   | V6.07    | [FastDFS](https://github.com/happyfish100/fastdfs/releases/tag/V6.07) |
| `ELK`       | 7.6.2    | [ELK Stack](https://www.elastic.co/guide/en/elastic-stack/7.6/index.html) |
| `MongoDB`   | 4.4.17   | [MongoDB](https://www.mongodb.com/try/download/community) |
| `Jenkins`   | latest   | [Jenkins](https://www.jenkins.io/zh/doc/book/installing/) |


## Special Thanks

The development of `zero-one-10wms` would not have been possible without the support of open-source software and the community. Special thanks to the following projects and their maintainers:

- `spring`: https://github.com/spring-projects
- `alibaba`: https://github.com/alibaba
- `mybatis`: https://github.com/mybatis/mybatis-3.git
- `vue`: https://github.com/vuejs
- `oatpp`: https://github.com/oatpp/oatpp

And many other open-source components and contributors who are not explicitly listed.
