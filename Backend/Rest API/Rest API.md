# Rest API

## Rest 란?

자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것을 의미 한다.

- 자원의 표현 
    + 자원:해당 소프트웨어가 관리하는 모든 것
    + 자원의 표현: 그 자원을 표현하기 위한 이름

- 상태(정보) 전달
    + 데이터가 요청되어지는 시점에 자원의 상태를 전달
    + JSON 혹은 XML를 통해 테이터를 주고 받는 것이 일반적

>네트워크 상에서 Client와 Server사이의 통신 방식 중 하나

## Rest의 장단점

장점
1. HTTP 프로토콜의 인프라를 그대로 사용하므로 REST API 사용을 위한 별도의 인프라를 구축할 필요가 없다.

2. HTTP 프로토콜의 표준을 최대한 활용하여 여러 추가적인 장점을 함께 가져갈 수 있게 해준다.

3. HTTP 표준 프로토콜에 따르는 모든 플랫폼에서 사용이 가능하다.

단점
1. 표준이 존재하지 않음

2. 사용할 수 있는 메소드가 4가지(HTTP Method) 뿐

3. 구형 브라우저에서 아직 제대로 지원해주지 못하는 부분이 존재

- PUT,DELETE를 사용하지못하는 점

## Rest API란?

API

>데이터와 기능의 집합을 제공하여 컴퓨터 프로그램간 상호작용을 촉진하며, 서로 정보를 교환가능 하도록 하는 것

REST API의 정의

- REST 기반으로 서비스 API를 구현한 것
- OpenAPI(누구나 사용할 수 있는 공개된 API) 는 대부분 REST API를 제공

## REST API의 설계 기본 규칙
URI는 자원의 정보를 표시해야 한다.
```java
GET /Member/1 ->GET /members/1
```

자원에 대한 행위는 HTTP Method(GET, PUT, POST, DELETE) 로 표현한다.

- URI에 HTTML Method가 들어가면 안된다

```java
GET /members/delete/1 -> DELETE /members/1
```

- URI에 행위에 대한 동사 표현이 들어가면 안된다(CRUD 기능을 나타내는 것은 URI에 사용하지 않는다.)

```java
GET /members/show/1 -> GET /members/1 
GET /members/insert/2 -> POST /members/2
```


