# SPring Bean

## Bean이란?

스프링 컨텡이너가 관리하는 자바 객체를 빈이라 한다.

스프링의 특징에는 `제어의 역전(IoC)`이 있다

>제어의 역전이란?
- 간단히 말해 객체의 생성 및 제어권을 사용자가 아니 스프링에게 맡기는 것이다.

## Bean을 스프링 컨테이너에 등록하는 방법

### 컴포너틑 스캔과 자동 의존관계 설정
@Component애노테이션이 있으면 스프링 빈으로 자동 등록 된다.  
또한,@Component를 포함하는 @Controller, @Service, @Repository 애노테이션도 스프링 빈으로 자동 등록된다.

회원관리 예제 코드
```java
package hello.hellospring.controller;

import hello.hellospring.service.MemberService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;

@Controller
public class MemberController {

    private final MemberService memberService;

	@Autowired
    public MemberController(MemberService memberService) {
        this.memberService = memberService;
    }
}
```

@Autowired
- 생성자에 @Autowired가 있으면 스프링이 연관된 객체를 스프링 컨테이너에 찾아서 넣어준다.

### 자바코드로 직접 스프링 빈 등록하기

@Configuration과 @Bean 애노테이션을 이용해 스프링 빈을 등록한다. @Configuration을 이용하면 스프링 프로젝터에서 Configuration 역할을 하는 Class를 지정할 수 있다.

회원 관리 예제 때는 개발자가 테스트에서 직접 주입했고, 여기서는 @Autowired에 의해 스프링이 주입해준다.

이 상태로 서버를 작동시키면 오류가 발생할 것이다.

<img src="photo.png">

바로 memberService가 스프링 컨테이너에 스프링 빈으로 등록되어 있지 않기 때문이다.
memberService도 스프링 빈으로 등록해주어야 한다.
***
```java
@Service
public class MemberService {

	private final MemberRepository memberRepository;

	@Autowired
	public MemberService(MemberRepository memberRepository) {
		this.memberRepository = memberRepository;
	}
}
```
***
memberRepository도 스프링 빈으로 등록해야 한다.
***

@Repository
public class MemoryMemberRepository implements MemberRepository {}

```java
package hello.hellospring.service;

import hello.hellospring.repository.MemberRepository;
import hello.hellospring.repository.MemoryMemberRepository;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class SpringConfig {

    @Bean
    public  MemberService memberService() {
        return new MemberService(memberRepository());
    }

    @Bean
    public MemberRepository memberRepository() {
        return new MemoryMemberRepository();
    }
}

```
.