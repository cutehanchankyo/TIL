# application.yml

## application.yml이란?

> application 및 spring의 설정에서 사용할 여러가지 property를 정의한 파일이다.yml은 형식이며 다른 형식(.properties, .ini등) 으로도 표현이 가능하다.

## 위치

```
src/main/resources
```

## 특징

- 들여쓰기(띄어쓰기)로 구부하여 보기 편하다.
- profile을 지정해서 환경에 따라 설정을 다르게 할 수 있다.
- 파일 형식은 .yml, .yaml 둘다 가능하다.
- Spring에선 pom.xml 에서 설정을 해야하지만, spring Boot에서는 자동으로 찾아준다.
- `---`을 사용해서 설정값을 구분한다.

## 구성

- 실행할 환경
- 실행할 포트 번호
- 연결할 DB접속 정보
- JPA 세부 세팅
- 콘솔 사용 여부
- 파라미터 확인 등등


## 예시) h2,jpa설정이 들어간 application.yml

```yml
spring:
    #DV연결
    datasource:
    # 설치된 H2 DB와 연결 URL
    #url: jdbc:h2:tcp://localhost/~/test #tcp모드
    url: jdbc:h2:mem:testdb;MODE=MySQL #인메모리모드
    #접속을 위한 드라이버
    dirver-class-name: org.h2.Driver
    username: sa

h2:
    console:
      enabled: true
    # 웹에서 sql 접근 가능
      path: /h2-console
jpa:
    # jpa가 수행하는 SQL을 볼 수 있다
    show-sql: true
    # 객체를 보고 자동으로 테이블 생성 여부. 생성 - create, 비생성 - none
    # 테스트이기 때문에 create로 설정
    # 실제로는 none, create이면 기존의 테이블을 전부 밀어버린다.
    hibernate:
        ddl-auto: create
    # 콘솔확인
    output:
      ansi:
        enabled: always
    # 데이터베이스 유형을 알려주는 것이 Dialect설정
    properties:
      hibernate:
        dialect: org.hibernate.dialect.MySQL5InnoDBDialect
# 파라미터 확인
logging:
  level:
    org.hibernate.type: trace

```


## 예시) 여러개의 yml설정 파일을 가지고 올때
위에 적은 파일명 순서대로 읽는다.
그래서 가장 아래 적힌 파일이 우선순위가 높다.
```yml
spring:
    config:
        import:
            - classpath:/a-config.yml
            - classpath:/b-config.yml #b-config.yml이 우선순위 높음
```