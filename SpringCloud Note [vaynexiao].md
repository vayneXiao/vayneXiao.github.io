# 微服务

```bash
什么是微服务？
就目前而言，对于微服务，业界并没有一个统一的，标准的定义
但通常而言，微服务架构是一种架构模式，或者说是一种架构风格， 它提倡将单一的应用程序划分成一
组小的服务，每个服务运行在其独立的自己的进程内，服务之间互相协调，互相配置，为用户提供最终
价值。服务之间采用轻量级的通信机制互相沟通，每个服务都围绕着具体的业务进行构建，并且能够被
独立的部署到生产环境中，另外，应尽量避免统一的，集中式的服务管理机制，对具体的一个服务而
言，应根据业务上下文，选择合适的语言，工具对其进行构建，可以有一个非常轻量级的集中式管理来
协调这些服务，可以使用不同的语言来编写服务，也可以使用不同的数据存储；

可能有的人觉得官方的话太过生涩，我们从技术维度来理解下：
微服务化的核心就是将传统的一站式应用，根据业务拆分成多个服务，彻底去耦合，
每一个微服务提供单个业务功能的服务，一个服务做一件事情，从技术角度看就是一种小而独立的处理过程，
类似进程的概念，能够自行单独启动或销毁。

微服务
强调的是服务的大小，他关注的是某一个点，是具体解决某一个问题/提供落地对应服务的一个服务应
用，狭义的看，可以看做是IDEA中的一个个微服务工程，或者Moudel

微服务架构
一种新的架构形式，Martin Fowler，2014提出！
微服务架构是一种架构模式，它提倡将单一应用程序划分成一组小的服务，服务之间互相协调，互相配
合，为用户提供最终价值。每个服务运行在其独立的进程中，服务于服务间采用轻量级的通信机制互相
协作，每个服务都围绕着具体的业务进行构建，并且能够被独立的部署到生产环境中，另外，应尽量避
免统一的，集中式的服务管理机制，对具体的一个服务而言，应根据业务上下文，选择合适的语言，工
具对其进行构建。

优点
    每个服务足够内聚，足够小，代码容易理解，这样能聚焦一个指定的业务功能或业务需求；
    开发简单，开发效率提高，一个服务可能就是专一的只干一件事；
    微服务能够被小团队单独开发，这个小团队是2~5人的开发人员组成；
    微服务是松耦合的，是有功能意义的服务，无论是在开发阶段或部署阶段都是独立的。
    微服务能使用不同的语言开发。
    易于和第三方集成，微服务允许容易且灵活的方式集成自动部署，通过持续集成工具，如jenkins
    微服务容易被开发人员理解，修改和维护，这样小团队能够更关注自己的工作成果。无需通过合作才能体现价值。
    微服务允许你利用融合最新技术。
    微服务只是业务逻辑的代码，不会和 HTML，CSS 或其他界面混合
    每个微服务都有自己的存储能力，可以有自己的数据库，也可以有统一数据库

缺点：
    开发人员要处理分布式系统的复杂性
    多服务运维难度，随着服务的增加，运维的压力也在增大
    系统部署依赖
    服务间通信成本
    数据一致性
    系统集成测试
    性能监控....
```

```shell
为什么选择SpringCloud作为微服务架构
1、选型依据
    整体解决方案和框架成熟度
    社区热度
    可维护性
    学习曲线
2、当前各大IT公司用的微服务架构有哪些？
    阿里：dubbo+HFS
    京东：JSF
    新浪：Motan
    当当网 DubboX
    .......
3、各微服务框架对比

SpringCloud是什么
SpringCloud, 基于SpringBoot提供了一套微服务解决方案，包括服务注册与发现，配置中心，全链路监
控，服务网关，负载均衡，熔断器等组件，除了基于NetFlix的开源组件做高度抽象封装之外，还有一些
选型中立的开源组件。
SpringCloud利用SpringBoot的开发便利性，巧妙地简化了分布式系统基础设施的开发，SpringCloud为
开发人员提供了快速构建分布式系统的一些工具，包括配置管理，服务发现，断路器，路由，微代理，
事件总线，全局锁，决策竞选，分布式会话等等，他们都可以用SpringBoot的开发风格做到一键启动和
部署。
SpringBoot并没有重复造轮子，它只是将目前各家公司开发的比较成熟，经得起实际考研的服务框架组
合起来，通过SpringBoot风格进行再封装，屏蔽掉了复杂的配置和实现原理，最终给开发者留出了一套
简单易懂，易部署和易维护的分布式系统开发工具包
SpringCloud 是 分布式微服务架构下的一站式解决方案，是各个微服务架构落地技术的集合体，俗称微
服务全家桶。

SpringCloud和SpringBoot关系
SpringBoot专注于快速方便的开发单个个体微服务。
SpringCloud是关注全局的微服务协调整理治理框架，它将SpringBoot开发的一个个单体微服务整合并管理起来，
为各个微服务之间提供：配置管理，服务发现，断路器，路由，微代理，事件总线，全局锁，决策竞选，
分布式会话等等集成服务。
SpringBoot可以离开SpringClooud独立使用，开发项目，但是SpringCloud离不开SpringBoot，
属于依赖关系,SpringBoot专注于快速、方便的开发单个个体微服务，SpringCloud关注全局的服务治理框架
```

是一种架构模式

- 将应用的每个功能放到一个独立的服务中，每个服务对应一个进程
- 使用一组小型服务来开发单个应用，每个服务运行在独立的进程中，服务与服务之间通过HTTP的方式进行互相通信
- 每个服务都是一个可独立替换和独立升级的软件单元， 并且能够被独立的部署到生产环境

优点：

- 分而治之：单个服务功能内聚，复杂性低，方便团队的拆分和管理
- 可伸缩：能够单独的对指定的服务进行伸缩
- 迭代周期短：支持快速的迭代开发
- 独立部署，独立开发

缺点：

- 运维要求高：应用流程通常跨多个微服务，不易进行问题的定位
- 分布式的复杂性：微服务需要使用分布式，而由于分布式本身的复杂性，导致微服务架构也变得复杂起来

 

#  SpringCloud简介

- SpringCloud是一套完整的微服务解决方案，基于SpringBoot框架
- SpringCloud是一系列框架的有序集合，它利用SpringBoot的开发便利性简化了分布式系统的开发
- SpringCloud为开发人员提供了快速构建分布式系统的一些工具，如服务发现注册、配置中心、消息总线、负载均衡、断路器、数据监控等

2. 技术栈
 微服务之间通过HTTP的方式进行互相通信，此时Web API的设计就显得非常重要，会使用 Restful API设计方式

# Restful

```xml
Representational State Transfer，简称为REST， 即表现层状态转化

资源 Resources
指的是网络上的某个数据， 如一个文件、一种服务等

表现层 Representational
资源的表现层，指的是资源的具体呈现形式，如HTML、JSON等

状态转化 State Transfer
指的是状态变化，通过HTTP方法来实现：
  GET 获取资源
  POST 新建资源
  PUT 更新资源
  DELETE 删除资源

简单来说，客户端通过HTTP方法对服务器的资源进行操作， 实现表现层状态转化
```

Restful 是目前最流行的 API 设计规范，用于 Web 数据接口的设计

Restful API设计原则：

- 尽量将API 部署在一个专用的域名下，如 http://api.itany.com

- API的版本应该在URL中体现，如 http://api.itany.com/v2

- URL中不要使用动词，应使用资源名词，且使用名词的复数形式，如

| 功能           | 请求类型 | URL                              |
| -------------- | -------- | -------------------------------- |
| 获取用户列表   | GET      | http://api.baidu.com/v2/users    |
| 根据id获取用户 | GET      | http://api.baidu.com/v2/users/id |
| 添加用户       | POST     | http://api.baidu.com/v2/users    |
| 根据id删除用户 | DELETE   | http://api.baidu.com/v2/users/id |
| 修改用户       | PUT      | http://api.baidu.com/v2/users    |

注：简单来说，可以使用同一个 URL ，通过约定不同的 HTTP 方法来实施不同的业务

- 服务器响应时返回JSON对象，应包含HTTP状态码、消息、结果等，如

{code:200,message:"success",result:{id:1001,name:"tom"}}

- 最好在返回的结果中提供链接， 指向其他的API方法，使得用户不用查文档， 就能知道下一步该怎么做

[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-9C4f34JM-1606228445791)(C:\Users\vaynexiao\AppData\Roaming\Typora\typora-user-images\image-20201121001119494.png)]

# swagger2

```xml
通常情况下，我们会创建一份Restful API文档来记录所有的接口细节，
供其他开发人员使用提供的接口服务，但会存在以下的问题：
	• 接口众多，并且细节复杂
	• 需要根据接口的变化，不断修改API文档，非常麻烦，费时费力
Swagger2的出现就是为了解决上述的这些问题，减少创建API文档的工作量
	• 后端人员在代码里添加接口的说明内容，就能够生成可预览的API文档，无须再维护Word文档
	• 让维护文档和修改代码整合为一体，在修改代码逻辑的同时方便的修改文档说明
	• 提供了强大的页面测试功能，便于对接口进行测试
	
<!-- 核心依赖 -->
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger2</artifactId>
    <version>2.9.2</version>
</dependency>
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger-ui</artifactId>
    <version>2.9.2</version>
</dependency>
<!-- 只为了解决某个bug -->
<dependency>
    <groupId>io.swagger</groupId>
    <artifactId>swaggerannotations</artifactId>
    <version>1.5.21</version>
</dependency>
<dependency>
    <groupId>io.swagger</groupId>
    <artifactId>swaggermodels</artifactId>
    <version>1.5.21</version>
</dependency>
```

```java
//创建Swagger2配置类
@Configuration
@EnableSwagger2
public class Swagger2 {
        @Bean
        public Docket createRestApi() {
            return new Docket(DocumentationType.SWAGGER_2)
                    .apiInfo(apiInfo())
                    //.enable(false) //配置是否启用Swagger，如果是false，在浏览器将无法访问
                    .select()
                    .apis(RequestHandlerSelectors.basePackage("com.yss.ms.admin"))
                    .paths(PathSelectors.any())
                    .build();
        }
        private ApiInfo apiInfo() {
            return new ApiInfoBuilder()
                    .title("服务:发布为daocke镜像,权限管理，用户管理，页面管理，日志 后台 APIs")
                    .description("服务:发布为daocke镜像,权限管理，用户管理，页面管理，日志 后台")
                    .termsOfServiceUrl("http://ip:port/xxx/xxx")
                    .contact("程序猿")
                    .version("1.0")
                    .build();
        }
    }
```

```java
@Api：用在请求的类上，表示对类的说明
    tags="说明该类的作用，可以在UI界面上看到的注解"
    value="该参数没什么意义，在UI界面上也看到，所以不需要配置"

@ApiOperation：用在请求的方法上，说明方法的用途、作用
    value="说明方法的用途、作用"
    notes="方法的备注说明"

@ApiResponses：用于请求的方法上，表示一组响应
     @ApiResponse：用在@ApiResponses中，一般用于表达一个错误的响应信息
        code：数字，例如400
        message：信息，例如"请求参数没填好"
        response：抛出异常的类
@ApiResponses({
    @ApiResponse(code=400,message="请求参数没填好"),
    @ApiResponse(code=404,message="请求路径没有或页面跳转路径不对")
})

@ApiImplicitParams：用在请求的方法上，包含一组参数说明
     @ApiImplicitParam：用在 @ApiImplicitParams 注解中，指定一个请求参数的配置信息       
        name：参数名
        value：参数的汉字说明、解释
        required：参数是否必须传
        paramType：参数放在哪个地方
            · header --> 请求参数的获取：@RequestHeader
            · query --> 请求参数的获取：@RequestParam
            · path（用于restful接口）--> 请求参数的获取：@PathVariable
            · body（不常用）
            · form（不常用）    
        dataType：参数类型，默认String，其它值dataType="Integer"       
        defaultValue：参数的默认值
@ApiImplicitParams({
    @ApiImplicitParam(name="mobile",value="手机号",required=true,paramType="form"),
    @ApiImplicitParam(name="password",value="密码",required=true,paramType="form"),
    @ApiImplicitParam(name="age",value="年龄",required=true,paramType="form",dataType="Integer")
})
    
@ApiModel 标注在模型Model上，比如User Dept对模型进行说明
	@ApiModelProperty
@ApiModel(description= "返回响应数据")
public class RestMessage implements Serializable{
    @ApiModelProperty(value = "是否成功")
    private boolean success=true;
}

@ApiIgnore 标注在类或方法上，表示忽略这个类或方法
    
http://ip:port/swaggerui.html
```

# Eureka
父模块 子模块 是通过yml文件产生关联

## 父模块 pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.baidu</groupId>
    <artifactId>cpt</artifactId>
    <version>1.0-SNAPSHOT</version>
    <modules>
        <module>api</module>
        <module>provider-dept-8001</module>
        <module>comsumer-dept-8002</module>
        <module>eureka-7001</module>
        <module>eureka-7002</module>
        <module>eureka-7003</module>
    </modules>

    <packaging>pom</packaging>

    <properties>
        <junit.version>4.12</junit.version>
        <log4j.version>1.2.17</log4j.version>
        <lombok.version>1.16.18</lombok.version>
    </properties>

    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.cloud</groupId>
                <artifactId>spring-cloud-dependencies</artifactId>
                <version>Hoxton.RELEASE</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
            <!-- 注意：springboot是2.2.x,2.3.x   springcloud匹配的是H版本
                官方给出的兼容表：https://spring.io/projects/spring-cloud -->
            <!-- spring-boot-dependencies -->
            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-dependencies</artifactId>
                <version>2.2.5.RELEASE</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
            <dependency>
                <groupId>mysql</groupId>
                <artifactId>mysql-connector-java</artifactId>
                <version>5.1.47</version>
            </dependency>
            <dependency>
                <groupId>com.alibaba</groupId>
                <artifactId>druid</artifactId>
                <version>1.1.6</version>
            </dependency>
            <dependency>
                <groupId>org.mybatis.spring.boot</groupId>
                <artifactId>mybatis-spring-boot-starter</artifactId>
                <version>2.1.4</version>
            </dependency>
            <dependency>
                <groupId>junit</groupId>
                <artifactId>junit</artifactId>
                <version>${junit.version}</version>
            </dependency>
            <dependency>
                <groupId>log4j</groupId>
                <artifactId>log4j</artifactId>
                <version>${log4j.version}</version>
            </dependency>
            <dependency>
                <groupId>org.projectlombok</groupId>
                <artifactId>lombok</artifactId>
                <version>${lombok.version}</version>
            </dependency>
            <dependency>
                <groupId>org.mybatis.spring.boot</groupId>
                <artifactId>mybatis-spring-boot-starter</artifactId>
                <version>1.3.0</version>
            </dependency>
            <dependency>
                <groupId>ch.qos.logback</groupId>
                <artifactId>logback-core</artifactId>
                <version>1.2.3</version>
            </dependency>
        </dependencies>
    </dependencyManagement>

</project>
```

## api模块

### Dept.java

api模块只提供一个实体类Dept

```java
public class Dept implements Serializable {

    private Long deptno; //主键
    private String dname; //部门名称
    // 来自哪个数据库，因为微服务架构可以一个服务对应一个数据库，同一个信息被存到多个不同的 数据库
    private String db_source;

    public Dept() {
    }

    public Dept(String dname) {
        this.dname = dname;
    }

    public Long getDeptno() {
        return deptno;
    }

    public void setDeptno(Long deptno) {
        this.deptno = deptno;
    }

    public String getDname() {
        return dname;
    }

    public void setDname(String dname) {
        this.dname = dname;
    }

    public String getDb_source() {
        return db_source;
    }

    public void setDb_source(String db_source) {
        this.db_source = db_source;
    }

    public Dept(Long deptno, String dname, String db_source) {
        this.deptno = deptno;
        this.dname = dname;
        this.db_source = db_source;
    }

}
```



## provider-dept-8001模块

### sql

```sql
CREATE TABLE `dept` (
  `deptno` int(11) NOT NULL AUTO_INCREMENT,
  `dname` varchar(255) DEFAULT NULL,
  `db_source` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`deptno`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8;

insert into dept (dname, db_source) values ('开发部', DATABASE());
```

### pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>cpt</artifactId>
        <groupId>com.baidu</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.baidu</groupId>
    <artifactId>provider-dept-8001</artifactId>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-actuator</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-eureka</artifactId>
            <version>1.4.7.RELEASE</version>
        </dependency>
        <!--引入自定义的模块，我们就可以使用这个模块中的类了-->
        <dependency>
            <groupId>com.baidu</groupId>
            <artifactId>api</artifactId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId> </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
        </dependency>
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid</artifactId>
        </dependency>
        <dependency>
            <groupId>ch.qos.logback</groupId>
            <artifactId>logback-core</artifactId>
        </dependency>
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
        </dependency>
        <dependency>
            <groupId>org.mybatis.spring.boot</groupId>
            <artifactId>mybatis-spring-boot-starter</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-jetty</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-test</artifactId>
        </dependency>

    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <version>2.3.4.RELEASE</version>
                <configuration>
                    <fork>true</fork>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <configuration>
                    <source>6</source>
                    <target>6</target>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <configuration>
                    <source>5</source>
                    <target>5</target>
                </configuration>
            </plugin>
        </plugins>
        <finalName>robot</finalName>
        <resources>
            <resource>
                <directory>src/main/webapp</directory>
            </resource>
            <resource>
                <directory>src/main/resources</directory>
            </resource>
            <resource>
                <directory>src/main/java</directory>
                <includes>
                    <include>**/*.xml</include>
                </includes>
            </resource>
        </resources>
    </build>

</project>
```

### application.yml

```yml
server:
 port: 8001

#mybatis的配置
mybatis:
  type-aliases-package: com.baidu.springCloud.pojo
  # 此后mapper.xml可以直接简写类名为User，不用写全类名
  # 注意和mybatis-config.xml中typeAliases不一样，这个会默认类名首字母小写
  config-location: classpath:mybatis/mybatis-config.xml
  mapper-locations: classpath:mybatis/mapper/*.xml

#spring的相关配置
spring:
  application:
    name: springcloud-provider-dept
  datasource:
    type: com.alibaba.druid.pool.DruidDataSource # 数据源
    driver-class-name: org.gjt.mm.mysql.Driver # mysql驱动
    url: jdbc:mysql://localhost:3306/api #数据库名称
    username: root
    password: 123456
    dbcp2:
      min-idle: 5  #数据库连接池的最小维持连接数
      initial-size: 5 #初始化连接数
      max-total: 5 #最大连接数
      max-wait-millis: 200  #等待连接获取的最大超时时间

#eureka配置
eureka:
 client:
  service-url:
   defaultZone: http://eureka7001.com:7001/eureka/,http://eureka7002.com:7002/eureka/,http://eureka7003.com:7003/eureka/
 instance:
   instance-id: provider-dept-8001
   prefer-ip-address: true # true访问路径可以显示IP地址

info:
  author: vaunexiao
```

###  mybatis-config.xml

resource 下

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">

<configuration>
    <settings>
        <setting name="cacheEnabled" value="true"/>
    </settings>

</configuration>
```

### DeptMapper.xml

resource - mapper  下

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN" 
"http://mybatis.org/dtd/mybatis-3-mapper.dtd">

<mapper namespace="com.baidu.cpt.dao.DeptDao">

    <insert id="addDept" parameterType="com.baidu.cpt.pojo.Dept">
        insert into dept (dname,db_source) values (#{dname},DATABASE());
    </insert>

    <select id="queryById" resultType="com.baidu.cpt.pojo.Dept" parameterType="Long">
        select deptno,dname,db_source from dept where deptno = #{deptno};
    </select>

    <select id="queryAll" resultType="com.baidu.cpt.pojo.Dept">
        select deptno,dname,db_source from dept;
    </select>

</mapper>
```

pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>cpt</artifactId>
        <groupId>com.baidu</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.baidu</groupId>
    <artifactId>provider-dept-8001</artifactId>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-actuator</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-eureka</artifactId>
            <version>1.4.7.RELEASE</version>
        </dependency>
        <!--引入自定义的模块，我们就可以使用这个模块中的类了-->
        <dependency>
            <groupId>com.baidu</groupId>
            <artifactId>api</artifactId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId> </dependency>
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
        </dependency>
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid</artifactId>
        </dependency>
        <dependency>
            <groupId>ch.qos.logback</groupId>
            <artifactId>logback-core</artifactId>
        </dependency>
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
        </dependency>
        <dependency>
            <groupId>org.mybatis.spring.boot</groupId>
            <artifactId>mybatis-spring-boot-starter</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-jetty</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-test</artifactId>
        </dependency>

    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <version>2.3.4.RELEASE</version>
                <configuration>
                    <fork>true</fork>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <configuration>
                    <source>6</source>
                    <target>6</target>
                </configuration>
            </plugin>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <configuration>
                    <source>5</source>
                    <target>5</target>
                </configuration>
            </plugin>
        </plugins>
        <finalName>robot</finalName>
        <resources>
            <resource>
                <directory>src/main/webapp</directory>
            </resource>
            <resource>
                <directory>src/main/resources</directory>
            </resource>
            <resource>
                <directory>src/main/java</directory>
                <includes>
                    <include>**/*.xml</include>
                </includes>
            </resource>
        </resources>
    </build>

</project>
```

### DeptController.java

```java
package com.baidu.cpt.controller;

import com.baidu.cpt.service.DeptService;
import com.baidu.cpt.pojo.Dept;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.cloud.client.ServiceInstance;
import org.springframework.cloud.client.discovery.DiscoveryClient;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/dept")
public class DeptController {

    @Autowired
    private DeptService service;

    @Autowired
    private DiscoveryClient client;

    // 如果参数是放在请求体中，传入后台的话，那么后台要用@RequestBody才能接收到
    @PostMapping("/add")
    public boolean addDept(@RequestBody Dept dept) {
        return service.addDept(dept);
    }

    @GetMapping("/get/{id}")
    public Dept get(@PathVariable("id") Long id) {
        return service.queryById(id);
    }

    @GetMapping("/list")
    public List<Dept> queryAll() {
        return service.queryAll();
    }

    @RequestMapping("/hello")
    public String hello(){
        return "hello";
    }

    @GetMapping("/discovery")
    public Object discovery(){
        //获得微服务列表清单
        List<String> list = client.getServices();
        System.out.println("client.getServices()==>"+list);
        //得到一个具体的微服务！
        List<ServiceInstance> serviceInstanceList = client.getInstances("springcloud-provider-dept");
        for (ServiceInstance serviceInstance : serviceInstanceList) {
            System.out.println(
                    serviceInstance.getServiceId()+"\t"+ serviceInstance.getHost()+"\t"+
                            serviceInstance.getPort()+"\t"+ serviceInstance.getUri() );
        }
        return this.client;
    }

}
```

### DeptDao.java

```java
package com.baidu.cpt.dao;

import com.baidu.cpt.pojo.Dept;
import org.apache.ibatis.annotations.Mapper;
import java.util.List;

@Mapper
public interface DeptDao {
    public boolean addDept(Dept dept); //添加一个部门
    public Dept queryById(Long id); //根据id查询部门
    public List<Dept> queryAll(); // 查询所有部门
}
```

### DeptService.java

```java
package com.baidu.cpt.service;

import com.baidu.cpt.pojo.Dept;
import java.util.List;

public interface DeptService {
    public boolean addDept(Dept dept); //添加一个部门
    public Dept queryById(Long id); //根据id查询部门
    public List<Dept> queryAll(); //查询所有部门
}
```

### DeptServiceImpl.java

```java
package com.baidu.cpt.service;

import com.baidu.cpt.dao.DeptDao;
import com.baidu.cpt.pojo.Dept;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;
import java.util.List;

@Service
public class DeptServiceImpl implements DeptService{

    @Autowired
    private DeptDao deptDao;

    @Override
    public boolean addDept(Dept dept) {
        return deptDao.addDept(dept);
    }

    @Override
    public Dept queryById(Long id) {
        return deptDao.queryById(id);
    }

    @Override
    public List<Dept> queryAll() {
        return deptDao.queryAll();
    }

}
```

### ProviderDept8001.java

```java
@SpringBootApplication
@EnableEurekaClient //启动后会自动注册到eureka中
//@EnableDiscoveryClient // 这个不加似乎也可以
public class ProviderDept8001 {
    public static void main(String[] args) {
        //启动测试前，应先启动provider模块
        SpringApplication.run(ProviderDept8001.class,args);
    }
}
```

## comsumer-dept-8002模块

### pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>cpt</artifactId>
        <groupId>com.baidu</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>comsumer-dept-8002</artifactId>

    <dependencies>
        <dependency>
            <groupId>com.baidu</groupId>
            <artifactId>api</artifactId>
            <version>1.0-SNAPSHOT</version>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-devtools</artifactId>
        </dependency>
    </dependencies>

</project>
```

### application.yml

```yml
server:
 port: 8002
```

### ConfigBean.java

```java
package com.baidu.cpt.config;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.web.client.RestTemplate;

@Configuration //相当于spring的applicationContext.xml来配置bean
public class ConfigBean {
	//RestTemplate这个类没有被spring默认配置为bean，需要手动使用@Configuration的配置类来配置成bean
    @Bean
    public RestTemplate getRestTemplate(){
        return new RestTemplate();
    }

}
```

### DeptConsumerController.java

```java
import org.springframework.web.client.RestTemplate;

@RestController
public class DeptConsumerController {
    //理解：消费者，不应该有service层
    // 使用RestTemplate访问restful接口非常的简单粗暴且无脑
    // （url，requestMap，ResponseBean.class） 这三个参数分别代表
    // REST请求地址，请求参数，Http响应转换 被 转换成的对象类型
    @Autowired
    private RestTemplate restTemplate;

    private static final String REST_URL_PREFIX = "http://localhost:8001";

    @RequestMapping("/consumer/dept/add")
    public boolean add(Dept dept){
        return restTemplate.postForObject(REST_URL_PREFIX+"/dept/add", dept, Boolean.class);
    }

    @RequestMapping("/consumer/dept/get/{id}")
    public Dept get(@PathVariable("id") Long id){
        return restTemplate.getForObject(REST_URL_PREFIX+"/dept/get/"+id, Dept.class);
        //return restTemplate.getForObject(REST_URL_PREFIX+"/dept/get/{id}"+, Dept.class, id);//没测试过
    }

    @RequestMapping("/consumer/dept/list")
    public List<Dept> list(){
        return restTemplate.getForObject(REST_URL_PREFIX+"/dept/list", List.class);
    }
//    RestTemplate提供了多种便捷访问远程Http服务的方法，是一种简单便捷的访问restful服务模板 类，
//    是Spring提供的用于访问Rest服务的客户端模板工具集
//
//    使用RestTemplate访问restful接口非常的简单粗暴且无脑
//    （url，requsetMap，ResponseBean.class） 这三个参数分别代表REST请求地址，请求参数， Http响应转换 被 转换成的对象类型
}
```

### ComsumerDept8002.java

```java
package com.baidu.cpt;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class ComsumerDept8002 {
    public static void main(String[] args) {
        SpringApplication.run(ComsumerDept8002.class,args);
    }
}
```

## eureka-7001模块

### pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>cpt</artifactId>
        <groupId>com.baidu</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>eureka-7001</artifactId>

    <dependencies>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-eureka-server</artifactId>
            <version>1.4.6.RELEASE</version>
        </dependency>
    </dependencies>

</project>
```

### application.yml

```properties
server:
 port: 7001

eureka:
 instance:
  hostname: eureka7001.com #eureka服务端的实例名称
  prefer-ip-address: true  #eureka页面鼠标悬浮实例名上后可以显示IP地址
 client:
  register-with-eureka: false  # 是否将自己注册到Eureka服务器中，本身是服务器，无 需注册
  fetch-registry: false # false表示自己端就是注册中心，我的职责就是维护服务实例，并 不需要去检索服务
  service-url: # 设置与Eureka Server交互的地址查询服务和注册服务都需要依赖这个defaultZone地址
   # 单机： defaultZone: http://${eureka.instance.hostname}:${server.port}/eureka/
   # 集群（关联）：
   defaultZone: http://eureka7002.com:7002/eureka/,http://eureka7003.com:7003/eureka/
   # Spring Cloud Eureka 常用配置及说明：https://www.cnblogs.com/li3807/p/7282492.html
```

### EurekaServer7001.java

```java
@SpringBootApplication
@EnableEurekaServer //EurekaServer服务器端启动类，接受其他微服务注册进来！
public class EurekaServer7001 {
    public static void main(String[] args) {
        SpringApplication.run(EurekaServer7001.class,args);
    }
}
```

## eureka-7002模块

### pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>cpt</artifactId>
        <groupId>com.baidu</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>eureka-7002</artifactId>

    <dependencies>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-eureka-server</artifactId>
            <version>1.4.6.RELEASE</version>
        </dependency>
    </dependencies>

</project>
```

### applicatuion.yml

```yml
server:
  port: 7002

#Eureka配置
eureka:
  instance:
    hostname: eureka7002.com #Eureka服务端的实例名称
  client:
    register-with-eureka: false # 表示是否向eureka注册中心注册自己
    fetch-registry: false #fetch-registry如果为false，则表示自己为注册中心
    service-url:  # 监控页面
      defaultZone: http://eureka7001.com:7001/eureka/,http://eureka7003.com:7003/eureka/
```

### EurekaServer7002.java

```java
@SpringBootApplication
@EnableEurekaServer //EurekaServer服务器端启动类，接受其他微服务注册进来！
public class EurekaServer7002 {
    public static void main(String[] args) {
        SpringApplication.run(EurekaServer7002.class,args);
    }
}
```

## eureka-7003模块

### pom.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <parent>
        <artifactId>cpt</artifactId>
        <groupId>com.baidu</groupId>
        <version>1.0-SNAPSHOT</version>
    </parent>
    <modelVersion>4.0.0</modelVersion>

    <artifactId>eureka-7003</artifactId>

    <dependencies>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-eureka-server</artifactId>
            <version>1.4.6.RELEASE</version>
        </dependency>
    </dependencies>

</project>
```

### applicatuion.yml

```yml
server:
  port: 7003

#Eureka配置
eureka:
  instance:
    hostname: eureka7003.com #Eureka服务端的实例名称
  client:
    register-with-eureka: false # 表示是否向eureka注册中心注册自己
    fetch-registry: false #fetch-registry如果为false，则表示自己为注册中心
    service-url:  # 监控页面~
      defaultZone: http://eureka7001.com:7001/eureka/,http://eureka7002.com:7002/eureka/
```

### EurekaServer7003.java

```java
@SpringBootApplication
@EnableEurekaServer //EurekaServer服务器端启动类，接受其他微服务注册进来！
public class EurekaServer7003 {
    public static void main(String[] args) {
        SpringApplication.run(EurekaServer7003.class,args);
    }
}
```

## 自我保护机制

修改一个服务名，故意制造错误，出现红色文本警告信息


一句话总结：某时刻某一个微服务不可以用了，eureka不会立刻清理，依旧会对该微服务的信息进行保存！

默认情况下，如果EurekaServer在一定时间内没有接收到某个微服务实例的心跳，EurekaServer将会注
销该实例（默认90秒）。但是当网络分区故障发生时，微服务与Eureka之间无法正常通行，以上行为可
能变得非常危险了--因为微服务本身其实是健康的，此时本不应该注销这个服务。Eureka通过 自我保护
机制 来解决这个问题--当EurekaServer节点在短时间内丢失过多客户端时（可能发生了网络分区故
障），那么这个节点就会进入自我保护模式。一旦进入该模式，EurekaServer就会保护服务注册表中的
信息，不再删除服务注册表中的数据（也就是不会注销任何微服务）。当网络故障恢复后，该EurekaServer节点会自动退出自我保护模式。

在自我保护模式中，EurekaServer会保护服务注册表中的信息，不再注销任何服务实例。当它收到的心
跳数重新恢复到阈值以上时，该EurekaServer节点就会自动退出自我保护模式。自我保护模式是一种应对网络异常的安全保护措施，它的设计哲学就是**宁可保留错误的服务注册信息（健康的微服务和不健康的微服务都会保留），也不盲目注销任何可能健康的服务实例。一句话：好死不如赖活着。可以让Eureka集群更加的健壮和稳定。**

在SpringCloud中，可以使用 eureka.server.enable-self-preservation = false 禁用自我保护模式 【不推荐关闭自我保护机制】

## Eureka集群
修改host文件，且编写多个eureka模块，互相之间关联，成为集群
C:\Windows\System32\drivers\etc
```xml
127.0.0.1 eureka7001.com
127.0.0.1 eureka7002.com
127.0.0.1 eureka7003.com
```

## CAP原则

```java
RDBMS （Mysql、Oracle、sqlServer）===>ACID
NoSQL（redis、mongdb）===> CAP
    
ACID是什么？
    A（Atomicity）原子性
    C（Consistency） 一致性
    I （Isolation）隔离性
    D（Durability）持久性 
    
CAP是什么？
    C（Consistency）强一致性
    A（Availability）可用性
    P（Partition tolerance）分区容错性

CAP理论的核心
	一个分布式系统不可能同时很好的满足一致性，可用性和分区容错性这三个需求。
	根据CAP原理，将NoSQL数据库分成了满足CA原则，满足CP原则和满足AP原则三大类：
        CA：单点集群，满足一致性，可用性的系统，通常可扩展性较差
        CP：满足一致性，分区容错性的系统，通常性能不是特别高
        AP：满足可用性，分区容错性的系统，通常可能对一致性要求低一些
```

## 对比Zookeeper

```xml
由于分区容错性P在分布式系统中是必须要保证的，因此我们只能在A和C之间进行权衡。
	Zookeeper保证的是CP；
	Eureka保证的是AP；

Zookeeper保证的是CP
    当向注册中心查询服务列表时，我们可以容忍注册中心返回的是几分钟以前的注册信息，但不能接受服
    务直接down掉不可用。也就是说，服务注册功能对可用性的要求要高于一致性。但是zk会出现这样一种
    情况，当master节点因为网络故障与其他节点失去联系时，剩余节点会重新进行leader选举。问题在
    于，选举leader的时间太长，30~120s，且选举期间整个zk集群都是不可用的，这就导致在选举期间注
    册服务瘫痪。在云部署的环境下，因为网络问题使得zk集群失去master节点是较大概率会发生的事件，
    虽然服务最终能够恢复，但是漫长的选举时间导致的注册长期不可用是不能容忍的。

Eureka保证的是AP
    Eureka看明白了这一点，因此在设计时就优先保证可用性。Eureka各个节点都是平等的，几个节点挂
    掉不会影响正常节点的工作，剩余的节点依然可以提供注册和查询服务。而Eureka的客户端在向某个
    Eureka注册时，如果发现连接失败，则会自动切换至其他节点，只要有一台Eureka还在，就能保住注册
    服务的可用性，只不过查到的信息可能不是最新的，除此之外，Eureka还有一种自我保护机制，如果在
    15分钟内超过85%的节点都没有正常的心跳，那么Eureka就认为客户端与注册中心出现了网络故障，此
    时会出现以下几种情况：
		1. Eureka不再从注册列表中移除因为长时间没收到心跳而应该过期的服务
		2. Eureka仍然能够接受新服务的注册和查询请求，但是不会被同步到其他节点上（即保证当前节点依
然可用）
		3. 当网络稳定时，当前实例新的注册信息会被同步到其他节点中

因此，Eureka可以很好的应对因网络故障导致部分节点失去联系的情况，而不会像zookeeper那样使整个注册服务瘫痪
```
# Feign
```sql
RestTemplate调用其他模块接口地址是写死的，使用Feigh解决
Feign是一个HTTP客户端，可以更快捷、优雅地调用HTTP服务，使编写HTTPClient变得更简单。
在Spring Cloud中使用Feign非常简单，只需要创建一个接口，然后在接口上添加一些注解就可以了。

Feign是声明式的web service客户端，它让微服务之间的调用变得更简单了，类似controller调用service。
Spring Cloud集成了Ribbon和Eureka，可在使用Feign时提供负载均衡的http客户端。
只需要创建一个接口，然后添加注解即可！
feign ，主要是社区，大家都习惯面向接口编程。这个是很多开发人员的规范。调用微服务访问两种方法

1. 微服务名字 【ribbon】
2. 接口和注解 【feign 】
```

1 编辑pom.xml文件，配置Feign和Eureka-Client依赖

```xml
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-openfeign</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
</dependency>
```

2 编辑启动类，启用Eureka客户端

```java
@SpringBootApplication
@EnableEurekaClient
@EnableFeignClients(basePackages = "com.xxx.xxx") // 启用Feign客户端，扫描指定包下所有的feign注解
public class CloudConsumer8080Application {
    public static void main(String[] args) {
        SpringApplication.run(CloudConsumer8080Application.class, args);
    }
}
```

3 创建interface并使用注解配置

```java
@FeignClient("user-provider") // 调用的服务名，到Eureka中寻找对应的微服务
@Service
public interface UserService {

   @GetMapping("/users/{id}")
   public ResponseResult getUser(@PathVariable(value = "id") Integer id);

   @PostMapping("/users")
   public ResponseResult postUser(@RequestParam("name") String name,@RequestParam("pwd") String pwd);

   @PutMapping("/users")
   public ResponseResult putUser(@RequestParam Map<String,Object> map);
}
```

4 Controller

```java
@RestController
public class DeptConsumerController {
    
  @Autowired
  private DeptClientService service = null;
    
  @RequestMapping("/consumer/dept/add")
  public boolean add(Dept dept){
    return this.service.addDept(dept);
  }
  @RequestMapping("/consumer/dept/get/{id}")
  public Dept get(@PathVariable("id") Long id){
    return this.service.queryById(id);
  }
  @RequestMapping("/consumer/dept/list")
  public List<Dept> list(){
    return this.service.queryAll();
  }
    
}
```

feign传递对象参数的解决方式：

- 方式一：将对象参数拆为多个简单类型参数，且必须添加@RequestParam注解
- 方式二：使用Map替代对象参数，且必须添加@RequestParam注解

通过Feign直接找到服务接口，由于在进行服务调用的时候融合了Ribbon技术，所以也支持负载均衡作用！
feign其实不是做负载均衡的,负载均衡是ribbon的功能,feign只是集成了ribbon而已,但是负载均衡的功能
还是feign内置的ribbon再做,而不是feign。默认轮询方式。

**Feign的作用的替代RestTemplate,性能比较低，但是简化了请求的编写，也使代码可读性提高**

# Hystrix

```txt
Hystrix是一个用于处理分布式系统的延迟和容错的开源库，在分布式系统里，许多依赖不可避免的会调
用失败，比如超时，异常等，Hystrix能够保证在一个依赖出问题的情况下，不会导致整体服务失败，避
免级联故障，以提高分布式系统的弹性。
    
“断路器” 本身是一种开关装置，当某个服务单元发生故障之后，通过断路器的故障监控（类似熔断保险
丝），向调用方返回一个服务预期的，可处理的备选响应（FallBack），而不是长时间的等待或者抛出
调用方法无法处理的异常，这样就可以保证了服务调用方的线程不会被长时间，不必要的占用，从而避
免了故障在分布式系统中的蔓延，乃至雪崩.

服务雪崩：在微服务架构中服务之间会相互调用和依赖，如果某个服务发生故障，可能会导致多个服务故障，从而导致整个系统故障（类似蝴蝶效应）
```

## 解决方式1：熔断（服务端）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201124223516103.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ZheW5lX3hpYW8=,size_16,color_FFFFFF,t_70#pic_center)
```xml
当服务出现不可用或响应超时时，为了防止整个系统出现雪崩， 暂时停止对该服务的调用，直接返回一个结果，
快速释放资源。
如果检测到目标服务情况好转，则恢复对目标服务的调用。（可理解为将故障服务暂时隔离）
当扇出链路的某个微服务不可用或者响应时间太长时，会进行服务的降级，进而熔断该节点微服务的调用，
快速返回 错误的响应信息。当检测到该节点微服务调用响应正常后恢复调用链路。在SpringCloud
框架里熔断机制通过Hystrix实现。Hystrix会监控微服务间调用的状况，当失败的调用到一定阈值，
缺省是5秒内20次调用失败就会启动熔断机制。
熔断机制的注解是 @HystrixCommand。
```
1， pom
```xml
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-hystrix</artifactId>
	<version>1.4.7.RELEASE</version>
</dependency>
```
2，Controller  @HystrixCommand(fallbackMethod = "方法名")
```java
@RestController
public class DeptController {
  @Autowired
  private DeptService service;
  //一旦调用服务方法失败并抛出了错误信息后
  // 会自动调用HystrixCommand标注好的fallbackMethod调用类中指定方法
  @GetMapping("/dept/get/{id}")
  @HystrixCommand(fallbackMethod = "processHystrix_Get")
  public Dept get(@PathVariable("id") Long id) {
    Dept dept = service.queryById(id);
    if (dept==null){
      throw new RuntimeException("该id："+id+"没有对应的的信息");
   }
    return dept;
 }
  public Dept processHystrix_Get(@PathVariable("id") Long id){
    return new Dept().setDeptno(id).setDname("该id："+id+"没有对应的信息，null--@HystrixCommand")
    	.setDb_source("no this database in MySQL");
      }
}
```
3，启动类增加注解

```java
@EnableCircuitBreaker //对hystrix 熔断机制的支持
```

## 解决方式2：降级（客户端）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201124223735271.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ZheW5lX3hpYW8=,size_16,color_FFFFFF,t_70#pic_center)

1， implements FallbackFactory<DeptClientService> 针对单个接口

```java
@Component //千万不要忘记
public class DeptClientServiceFallbackFactory implements
FallbackFactory<DeptClientService> {
  @Override
  public DeptClientService create(Throwable throwable) {
    return new DeptClientService() {
      @Override
      public Dept queryById(Long id) {
        return new Dept().setDeptno(id)
           .setDname("该id："+id+"没有对应的信息，Consumer客户端提供的降级信息，此刻服务Provider已经关闭")
           .setDb_source("no this database in MySQL");
     }
      @Override
      public List<Dept> queryAll() {
        return null;
     }
      @Override
      public boolean addDept(Dept dept) {
        return false;
     }
   };
 }
}
```

2，接口增加注解

```java
@FeignClient(value="PROVIDER-01",fallbackFactory=DeptClientServiceFallbackFactory.class)
public interface DeptClientService {
```

3，application.yml，启用断路器

```properties
feign:
 hystrix:
  enabled: true
```

## 测试

当服务提供者不可用或出现异常时，比如 int a = 5/0，会暂时停止对该服务的调用

## Dashboard

```xml
是一个独立项目

除了隔离依赖服务的调用以外，Hystrix还提供了准实时的调用监控（Hystrix Dashboard），Hystrix会
持续地记录所有通过Hystrix发起的请求的执行信息，并以统计报表和图形的形式展示给用户，包括每秒
执行多少请求，多少成功，多少失败等等。

Netflix通过hystrix-metrics-event-stream项目实现了对以上指标的监控，
SpringCloud也提供了HystrixDashboard的整合，对监控内容转化成可视化界面！
```

pom

```xml
<!--Hystrix-->
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-hystrix</artifactId>
	<version>1.4.7.RELEASE</version>
</dependency>
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-hystrix-dashboard</artifactId>
	<version>1.4.7.RELEASE</version>
</dependency>
```

application.yaml

```properties
server:
 port: 9001
```

主启动类改名 + 新注解@EnableHystrixDashboard

```java
@SpringBootApplication
@EnableHystrixDashboard
public class DeptConsumerDashBoardApp9001 {
	public static void main(String[] args) {
		SpringApplication.run(DeptConsumerDashBoardApp9001.class,args);
	}
}
```

所有的Provider微服务提供类(8001/8002/8003) 都需要监控依赖配置

```xml
<!--actuator监控信息完善-->
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```
http://localhost:9001/hystrix
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201124223833483.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ZheW5lX3hpYW8=,size_16,color_FFFFFF,t_70#pic_center)



# Zuul

```xml
Zuul本身也是一个项目，也会注册到Eureka

对请求的统一管理和处理，比如隐藏真实ip 端口 服务名等。

Zuul是一个路由网关Gateway，包含两大功能：
对请求的路由：将外部的请求转发到具体的微服务实例上，是实现外部访问统一入口的基础
对请求的过滤：对请求的处理过程进行干预，是实现请求校验、服务聚合等功能的基础

将Zuul和Eureka进行整合，把Zuul自身注册为Eureka服务治理下的应用，
同时从Eureka中获得其他微服务的信息，对于微服务的访问都要通过Zuul进行跳转
```

pom.xml 文件，配置依赖

```xml
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-eureka</artifactId>
    <version>1.4.7.RELEASE</version>
</dependency>
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>springcloud-starter-netflix-eureka-client</artifactId>
	<version>1.4.7.RELEASE</version> 
</dependency>
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>springcloud-starter-netflix-zuul</artifactId>
	<version>1.4.7.RELEASE</version>
</dependency>
```

启动类，@EnableZuulProxy

```java
@SpringBootApplication
@EnableZuulProxy // 启用Zuul，此注解是加强版，针对同时使用到eureka的情况
public class CloudZuul9001Application {
    public static void main(String[] args) {
        SpringApplication.run(CloudZuul9001Application.class, args);
    }
}
```

此时

application.yml，配置eureka和zuul

```properties
server:
    port: 6001
spring:
    application:
        name: zuulgateway
eureka:
    client:
        serviceurl:
            defaultZone: http://localhost:7001/eureka/
zuul: # 路由相关配置
    prefix: /v2 # 对每个微服务指定唯一的任意key值，比如v2版本号
    ignored-services: springcloud-provider-dept  
    # 不能再使用这个服务名访问，只可以用配置的path
    # ignored-services: "*" # 通配符*, 隐藏全部
    routes:  # 配置路由表
    user: # 对于每个微服务，可以自定义一个唯一的key值，该值可以任意指定
        path: /mydept/** # springcloud-provider-dept服务的路径全部转换为mydept
        serviceId: springcloud-provider-dept # 服务id
```
不用路由 ：http://localhost:8001/dept/get/2
使用路由 ：http://localhost:8001/mydept/dept/get/2

前面的localhost:8001也可以使用域名屏蔽

# Ribbon
Ribbon是一套客户端负载均衡的工具，用于实现微服务的负载均衡 Load Balance
Ribbon不需要独立部署，Feign集成了Ribbon，自动的实现了负载均衡，那还需要引入ribbon依赖吗

搭建Provider集群
不能使用tempPlate传固定地址开放问了，要根据服务名（可以使用Feigh）然后eureka配置了Ribbon后动态选择一个服务方。
拷贝 cloud-provider-8001 为 cloud-provider-8002 和 cloud-provide-r8003

pom

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-ribbon</artifactId>
  <version>1.4.7.RELEASE</version>
</dependency>
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-config</artifactId>
</dependency>
```

consumer 用Feigh无需设置，如果给Config类的Bean TempPlate加注解@LoadBalanced

```java
@Bean
@LoadBalanced //开启负载均衡的功能
RestTemplate restTemplate() {
    return new RestTemplate();
}
//为何一个@LoadBalanced注解就能让RestTemplate拥有负载均衡的能力？【享学Spring Cloud】
https://www.cnblogs.com/yourbatman/p/11532729.html
```

修改主启动类的类名(也要注册到eureka，所以@EnableEurekaClient)

```java
@RibbonClient(name="provider", configuration=MySelfRule.class)
```

application.yml配置：端口号和instanceid不同  name相同

```properties
server:
 port: 8002 # 不同的端口
 
spring:
 application:
  name: user-provider # 相同的服务名
  
 eureka:
  client:
   service-url:
    defaultzone: http://localhost:7001/eureka/
   instance:
    instance-id: user-provider8002 # 不同的实例id
```

默认使用的是 轮询策略

常见的策略：

- 轮询 (RoundRobinRule) （默认）
- 随机 (RandomRule)
- 响应时间权重（WeightedResponseTimeRule）响应时间越短的服务器被选中的可能性大
- 并发量最小可用（BestAvailableRule）选取最少并发量请求的服务器

改变负载均衡策略

在Zuul服务中，通过配置类指定要应用的负载均衡策略

```java
@Configuration
public class RibbonConfig {
    @Bean
    public IRule myRule(){
        return new RandomRule();
    }
}
```
# Config
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201125181358623.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ZheW5lX3hpYW8=,size_16,color_FFFFFF,t_70#pic_center)

## server

1、新建 maven 项目

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-eureka</artifactId>
	<version>1.4.7.RELEASE</version>
</dependency>
<!-- spring cloud config 服务端包 -->
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-config-server</artifactId>
</dependency>
```

2，application.yml

```properties
server:
  port: 3399  
spring:
  application:
    name: config-single-server  # 应用名称
  cloud:
     config:
        server:
          git:
            uri: https://github.com/huzhicheng/config-only-a-demo # http的git项目路径
            #username: github # 登录账号
            #password: github # 登录密码
            #default-label: master # 配置文件分支
            #search-paths: config  # 配置文件所在根目录
```

3、启动类增加注解@EnableConfigServer

4，测试

```html
/{application}/{profile}[/{label}]
/{application}-{profile}.yml
/{label}/{application}-{profile}.yml
/{application}-{profile}.properties
/{label}/{application}-{profile}.properties

{application} 就是应用名称，对应到配置文件上来，就是配置文件的名称部分，例如我上面创建的配置文件。

{profile} 就是配置文件的版本，我们的项目有开发版本、测试环境版本、生产环境版本，
对应到配置文件上来就是以 application-{profile}.yml 加以区分，
例如application-dev.yml、application-sit.yml、application-prod.yml。

{label} 表示 git 分支，默认是 master 分支，如果项目是以分支做区分也是可以的，
那就可以通过不同的 label 来控制访问不同的配置文件了。

上面的 5 条规则中，我们只看前三条，因为我这里的配置文件都是 yml 格式的。
根据这三条规则，我们可以通过以下地址查看配置文件内容:
http://localhost:3301/config-single-client/dev/master
http://localhost:3301/config-single-client/prod
http://localhost:3301/config-single-client-dev.yml
http://localhost:3301/config-single-client-prod.yml
http://localhost:3301/master/config-single-client-prod.yml

通过访问以上地址，如果可以正常返回数据，则说明配置中心服务端一切正常。
```

## client

1.pom

```xml
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-config</artifactId>
</dependency>

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

2 远程的client-provider-yml
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201125181448556.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ZheW5lX3hpYW8=,size_16,color_FFFFFF,t_70#pic_center)


3 本地项目yml，这一步表示和server通信

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201125181621882.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ZheW5lX3hpYW8=,size_16,color_FFFFFF,t_70#pic_center)
写一个controller，可以测试获取的信息是否拿到
```java
@RestController
public class ConfigClientController {

    @Value("${spring.application.name}")
    private String applicationName;

    @Value("${eureka.client.service-url.defaultZone}")
    private String eurekaServer;

    @Value("${server.port}")
    private String port;

    @RequestMapping("/config")
    public String getConfig(){
        return "applicationName:"+applicationName +
         "eurekaServer:"+eurekaServer + "port:"+port;
    }
}
```
