# Annotation

## Annotation 이란?

Annotation은 클래스와 메서드에 추가하여 다양한 기능을 부여하는 역할을 한다. Annotation을 활용하여 Spring Framework는 해당 클래스가 `어떤 역할인지 정하기도 하고`,Bean을 주입하기도 하며, 자동으로 getter나 setter를 생성하기도 한다, `특별한 의미를 부여하거나 기능을 부여하는 등` 다양한 역할을 수행할 수 있다.

## Spring의 대표적인 Annotation과 역할

1. @Component

>개발자가 생성한 Class를 Spring의 Bean으로 등록할때 사용하는 Annotation이다. Spring은 해당 Annotation을보고 Spring의 Bean으로 등혹한다.

```java
@Component(value="myman")
public class Man{
    public Man(){
        System.out.println("hello-spring");
    }
}
```

2. @Bean

>@Bean Annotation은 개발자가 제어가 불가능한 외부 라이브러리와 같은 것들을 Bean으로 만들 때 사용한다.

3. @Controller

>Spring에게 해당 Class가 Controller의 역할을 한다고 명시하기 위해 사용하는 Annotation이다.

```java
@Controller
@RequestMapping("/user")
public class UserController{
    @RequestMapping(method = RequesMethod.GET){
        // GET method, /user요청을 처리
    }
}
```

