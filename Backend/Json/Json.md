# Json

## Json(JavaScript Object Notation)이란?

Javascript 객체 문법으로 구조화된 데이터를 표현하기 위한 문자 기반의 표준 포맷입니다. 웹 어플리케이션에서 데이터를 전송할 때 일반적으로 사용합니다.

## Json 특징

1. 서버와 클라이언트 가의 교류에서 일반적으로 많이 사용된다.
2. 자바스크립트를 이용하여 Json 형식의 문서를 쉽게 자바스크립트 객체로 변환할 수 있는 이점이 있다.
3. 자바스크립트의 문법과 굉장히 유사하지만 텍스트 형식일 뿐이다.

## Json 문법

```java
{
    "employees": [
    {
      "name": "Surim",
      "lastName": "Son"
    },
    {
      "name": "Someone",
      "lastName": "Huh"
    },
    {
      "name": "Someone else",
      "lastName": "Kim"
    } 
  ]
}
```

>JSON 형식은 자바스크립트 객체와 마찬가지로 key / value가 존재할 수 있으며 key값이나 문자열은 항상 쌍따옴표를 이용하여 표기해야한다. 객체, 배열 등의 표기를 사용할 수 있다.

## Json 형식

1. name-value형식의 쌍
- 여러가지 언어들에서 object등으로 실현되었다.
- { String key : String value }

```java
{
  "firstName": "Kwon",
  "lastName": "YoungJae",
  "email": "kyoje11@gmail.com"
}
```

2. 값들의 순서화된 리스트 형식
- 여러가지 언어들에서 배열(Array) 등으로 실현되었다.
- [value1, value2, ...]

```java
{
  "firstName": "Kwon",
  "lastName": "YoungJae",
  "email": "kyoje11@gmail.com",
  "hobby": ["puzzles","swimming"]
}
```

## Json 단점

내용이 함축적이다 보니 의미 파악이 힘들 수가 있습니다.

경량의 데이터 교환 형식이기 때문에 XML보다 빠르지만, 대용량급의 데이터 송수신에는 부적합한 모습도 있습니다.