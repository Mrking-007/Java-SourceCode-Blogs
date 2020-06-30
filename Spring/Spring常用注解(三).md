# 1 Spring常用注解



# 2 Spring 注解注册bean

## 2.1 @Configuration

```java
@Import(ConditionConfig.class)//参见https://www.cnblogs.com/iiiiiher/p/12781618.html
@Configuration //该注解相当于xml
public class BasicConfig {
   @Bean//默认不指定名字，则bean id是返回值类型名字，该注解相当于xml中<bean id="student" name="getSut1" type="com.ymbj.config.Student"></bean>
   //@Primary
   public Student getStu1() {
      return new Student("小张", 12);
   }

   @Bean
   public Student getStu2() {
      return new Student("小李", 20);
   }
}

// id name https://www.cnblogs.com/xiewuqing/p/4678407.html
// bean name https://www.cnblogs.com/1540340840qls/p/6962777.html
// Spring创建bean默认的id值 https://www.jianshu.com/p/77d0ec46703c
//spring中bean配置和bean注入 https://www.cnblogs.com/wuchanming/p/5426746.html
```





## 2.2 @Bean

注意，形参默认使用@Autowire

xml name  type

## 2.3 @Import

## 2.4 @Primary

## 2.5 @Component

### 2.5.1 @Controller和@RestfulController

### 2.5.2 @Service 

### 2.5.3 @Repository

# 3 Spring 使用注解注入 

## 3.1 @Autoware和@Qualifier

默认是通过类型(byType)找bean，如存在多个类型则通过名称(byName)找bean

```java

```

三种解决方案

1、注册bean 使用@Primary

2、注册bean时指定注入时属性名称为bean name，覆盖name=默认方法名；这种不合适声明(注册)bean和使用(注入)耦合过密bean

3、注入时，使用@Qualifier注解显式指定bean name（推荐）

## 3.2 @Resource ?

首先`@Resource`不是Spring的注解，是JavaEE的注解，默认是先按照名称(byName)找bean,如名称无找到则通过类型(byType)

https://blog.csdn.net/weixin_40423597/article/details/80643990

https://www.yuque.com/docs/share/fe2e6770-216c-4ea8-a56c-3c94b90faf46