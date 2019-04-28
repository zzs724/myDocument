# SpringBoot

## 一、常用注解

- @SpringBootApplication启动类注解，包含了各种注解

- @SpringBootConfiguration 继承至@Configuration，标注当前类是配置类

- @EnableAutoConfiguration 自动加载注解。将所有符合自动配置条件的bean加载到spring容器

- @ComponentScan 扫描当前包及其子包下所有注解的类

- @Controller标志此类是一个Controller类

- **@RequestBody** ：**获取请求参数为json的数据**

  ```java
  public String test(@RequestBody Person person){
      //前端传的person为json格式数据
  }
  ```

- **@ResponseBody**：类或方法上，**此类所有的方法或者某方法返回json类型数据**

  ```java
  @RequestMapping("/test")
  @ResponseBody
  public Person test(){
      return Person;//页面显示Person为json格式
  }
  ```

- @RestController是@Controller+@ResponseBody的组合

- @RequestMapping：处理请求地址映射，类或方法上

- @GetMapping = @RequestMapping（method=“GET”）

- @PostMapping = @RequestMapping（method=“POST”）

- @PutMapping = @RequestMapping（method=“Put”）

- @DeleteMapping = @RequestMapping（method=“Delete”）

- @PatchMapping = @RequestMapping（method=“Patch”）

- @PathVariable 方法中用来接收参数。如：/path/3

  ```java
  @GetMapping("path/{id}")
  public String PathVariable (@PathVariable("id"String id)){
      return id;
  }
  ```

  

- @RequestParam 接收参数，如：/param?id=2

  ```java
  @GetMapping("/param")
  public String RequestParam  (@RequestParam ("id"String id)){
      return id;
  }
  ```

- @RequestAttribute：request.getAttrbute()

  ```java
  @GetMapping("/req/attr")
  public String reqAttr(@RequestAttribute("id"String id)){
       return id;
  }
  ```

- @Import：导入的类会成为配置类

- **@ImportResource：用来加载xml配置文件。**

- @Value：获取 application.properties/yml中的属性值

  ```xml
  my.name=zzz
  ```

  ```java
  @Value(value="${my.name}")
  private String name;
  ```

- **@PropertySource：读取配置文件**

  ```java
  @PropertySource({ "classpath:mail.properties", "classpath:db.properties" })
  @Value(value="${my.name}")
  private String name;
  ```

- @ConfigurationProperties：可以读取配置文件中自定义开头的属性

  ​		**将注解转换成对象。给对象赋值**

  ```xml
  person.name=zzz
  person.age=15
  ```

  ```java
  @ConfigurationProperties(prefix = "person")
  public class Person{
      private String name;
      private int age;
  }
  ```

- @EnablCaching：缓存

## 二、SpringBoot中常用的starter的组件

- spring-boot-starter-parent //boot项目继承的父项目模块.
- spring-boot-starter-web //boot项目集成web开发模块.
- spring-boot-starter-tomcat //boot项目集成tomcat内嵌服务器.
- spring-boot-starter-test //boot项目集成测试模块.
- mybatis-spring-boot-starter //boot项目集成mybatis框架.
- spring-boot-starter-jdbc //boot项目底层集成jdbc实现数据库操作支持.

## 三、SpringBoot项目兼容Spring集成的项目

利用@ImportResource({"classpath:spring1.xml" , "classpath:spring2.xml"})

## 四、加载外部配置文件属性

```java
@PropertySource(value ="classpath:user.properties")
@ConfigurationProperties(prefix = "user")
public class User{}
```

## 五、SpringBoot主配置类的注解

@SpringBootApplication

​	↓

@SpringBootConfiguration  ----->@Configuration

@EnableAutoConfiguration ----->@AutoConfigurationPackage,@Import

@ComponentScan

## 六、SpringBoot支持的日志框架

默认采用LogBack作为日志框架

logging.file=d:/test/log.log

logging.level.org.springframework.web=DEBUG

logging.config=classpath:logback.xml 加载单独的日志配置文件.

## 七、配置多环境配置文件及切换

​	application-dev.yml    application-prod.yml 

​	spring.profile.active=dev  切换

