# Optional

## Optional 이란?
>null 일 수도 있는 객체를 감싸는 일종의 Wrapper 클래스이다.

```java
Optional <t> optional
```

- optional 변수 내부에는 null이 아닌 T 객체가 있을 수도 있고 null이 있을 수도 있다.  따라서, Optional 클래스는 여러가지 API를 제공하여 null일 수도 있는 객체를 다룰 수 있도록 돕는다.

1)Optional 객체 생성

```java
Optional<User> result = userRepository.findById(userId);
```

2)Optional 객체 접근

```java
if(result.is present()){
    retrun result.get();
}

else{
    retrun result.orElse(null);
} 
```

- et() : Optional 내부에 담긴 객체를 반환합니다. 만약, null인 객체라면 NoSuchElementException이 발생합니다. 따라서, isPresent() 로 체크한 후에 이 get 메서드를 사용

- orElse(): 있으면 값을 반환하고, 그렇지 않으면 다른 값을 반환