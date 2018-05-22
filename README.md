# springboot_3_thymeleaf
springboot推荐的thymeleaf模板demo

## maven配置
>pom.xml   

```xml
<!--引入thymeleaf-->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>
```
## thymeleaf配置


```properties
#thymeleaf start
#注释的为thymeleaf的默认配置,可以不需要配置该项
#spring.thymeleaf.mode=HTML
#spring.thymeleaf.encoding=UTF-8
#spring.thymeleaf.servlet.content-type=text/html
#开发时关闭缓存,不然没法看到实时页面
spring.thymeleaf.cache=false

#thymeleaf end
```
## thymeleaf模板demo

```html
<!DOCTYPE HTML>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>hello</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
    <!--/*@thymesVar id="name" type="java.lang.String"*/-->
    <p th:text="'Hello！, ' + ${name} + '!'" >3333</p>
</body>
</html>
```
## Controller

``` java
@RequestMapping("/{name}")
String index(@PathVariable("name") String name, Model model){
    model.addAttribute("name", name);
    return "index";
}
```
