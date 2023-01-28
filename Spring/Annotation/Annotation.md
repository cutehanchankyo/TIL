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

4. @RequestHeader

> Request의 header값을 가져올 수 있으며, 해당 Annotation을 쓴 메소드의 파라미터에 사용한다.

5. RequestMappring

>@RequestMapping(value="")와 같은 형태로 작성하며, 요청 들어온 URI의 요청과 Annotation value 값이 일치하면 해당 클래스나 메소드가 실행됩니다, Controller 객체 안의 메서드와 클래스에 적용 가능하며, 아래와 같이 사용한다.

- Class 단위에 사용하면 하위 메소드에 모두 적용된다,
- 메소드에 적용되면 해당 메소드에서 지정한 방식으로 URI를 처리한다.
```java
@Controller
@RequestMapping("/user")
public class UserController{
    @RequestMappring(method = RequestMEthod.GET)
    public String getUser(Model model){
        // Get method, /user 요청을 처리
    }
    @RequestMappring(method = RequestMEthod.Post)
    public String addUser(Model model){
        //Post method, /user 요청을 처리
    }
    @RequestMappring(value = "/info", method = RequestMEthod.GET)
    public String addUser(Model model){
        //Get method,/user/info 요청을 처리
    }


}
```

6. @RequestParam

>URL에 전달되는 파라미터를 메소드의 인자와 매칭시켜, 파라미터를 받아서 처리할 수 있는Annotation으로 아래와 같이 사용한다. Json형식의 Body를 MessageConverter를 통해 java객체로 변환시킨다.

7. @RequestBody

>Body에 전달되는 데이터를 메소의 인자와 매칭시켜, 데이터를 받아서 처리할 수 있는 Annotation으로 아래와 같이 사용합니다. 클라이언트가 보내는 HTTP 요청 본문(JSON 및 XML)을 java 오브젝트로 변환한다.

클라이언트가 body에 json or xml과 같은 형태로 값을 전송하면, 해당 내용을 java Objec로 변환한다.

```java
@Controller
@RequesMapping("/user")
public class UserCOntroller{
    @RequestMapping(method = RequestMethod.Post)
    public String addUSer(@RequestBody User user){
        //Post method, /user 요청을 처리
        String sub_name = user.name;
        String sub_old = user.old;
    }
}
```

8. @ResponseBody
>@ResponseBody는 메소드에서 리턴되는 값이 View로 출력되지 않고 HTTP Response Body에 직접 쓰여 지게 됩니다. retur 시에 json, xml과 같은 데이터를 return한다.

```java
@Controller                   // 이 Class는 Controller 역할을 합니다
@RequestMapping("/user")      // 이 Class는 /user로 들어오는 요청을 모두 처리합니다.
public class UserController {
    @RequestMapping(method = RequestMethod.GET)
    @ResponseBody
    public String getUser(@RequestParam String nickname, @RequestParam(name="old")) String age {
        // GET method, /user 요청을 처리
        User user = new User();
        user.setName(nickname);
        user.setAge(age);
        return user;
    }
}
```

9. GetMapping
>RequestMapping(Method=RequestMethod.GET)과 똑같은 역할을 하며, 아래와 같이 사용합니다.
```java

@Controller                   // 이 Class는 Controller 역할을 합니다
@RequestMapping("/user")      // 이 Class는 /user로 들어오는 요청을 모두 처리합니다.
public class UserController {
    @GetMapping("/")
    public String getUser(Model model) {
        //  GET method, /user 요청을 처리
    }
    
    ////////////////////////////////////
    // 위와 아래 메소드는 동일하게 동작합니다. //
    ////////////////////////////////////

    @RequestMapping(method = RequestMethod.GET)
    public String getUser(Model model) {
        //  GET method, /user 요청을 처리
    }
}
```

10. @PostMapping
> RequestMapping(Method=RequestMethod.POST)과 똑같은 역할을 하며, 아래와 같이 사용합니다.
```java
@Controller                   // 이 Class는 Controller 역할을 합니다
@RequestMapping("/user")      // 이 Class는 /user로 들어오는 요청을 모두 처리합니다.
public class UserController {
    @RequestMapping(method = RequestMethod.POST)
    public String addUser(Model model) {
        //  POST method, /user 요청을 처리
    }

    ////////////////////////////////////
    // 위와 아래 메소드는 동일하게 동작합니다. //
    ////////////////////////////////////

    @PostMapping('/')
    public String addUser(Model model) {
        //  POST method, /user 요청을 처리
    }
}
```
