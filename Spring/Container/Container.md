# Spring Container

## Container란?

스츠링의 빈을 생성하고 관리하는 컨테이너를 가지고 있다,
이를 통해서 스프링의 주개념인 Ioc나 AOP에 대해서 관리한다,

## Container의 종류

스프링 컨테이너의 종류는 Bean Factory와 이를 상속한 ApplicationContext 2가지 유형이 존재한다.

### Bean Factory
>Bean Factory는 스프링 설정파일에 등록된 Bean 객체를 생성하고 관리하는 기본적인 기능만 제공한다.

- 컨테이너가 구동될 때 Bean 객체를 생성하는 것이 아니라 클라이언트의 요청에 의해서 Bean 객체가 사용되는 시점(Lazy Loading) 에 객체를 생성하는 방식을 사용하고 있다.


### Application Context

>Bean Factory와 마찬가지로, Bean 객체를 생성하고 관리하는 기능을 가지고 있다.

- 뿐만 아니라 트랜잭션 관리, 메시지 기반의 다국어 처리, AOP 처리등등 DI(Dependency Injection) 과 Ioc(Inverse of Conversion) 외에도 많은 부분을 지원하고 있다.



