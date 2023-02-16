# 비교와Boolean

## Boolean
불린은 참과 거짓을 의미하는 데이터 타입으로 boll이라고 부른다 불린은 정수나 문자와 같이 하나의 데이터 타입인데, 삼을 의미하는 true와 거짓을 의미하는 false 두 가지의 값을 가지고 있다. 

## 비교 연산자
프로그래밍에서 비교란 주어진 값들이 같은지, 다른지, 큰지, 작은지를 구분하는 것을 의미한다. 이때 비교 연산자를 사용한는데 비교 연산자의 결과는 true나false중의 하나다.

## ==
좌향과 우햐을 비교해서 서로 값이 같아면 true다르다면 false가된다. `=`이 두 개인 것을 주의하자. `=`이 한인 것은 대입 연산자로 우향의 값을 좌향의 변수에 대입할 때 사용하는 것으로 의미가 완줜히 다르다.

```java
    System.out.println(1==2);           //false
    System.out.println(1==1);           //true
    System.out.println("one"=="two");   //false
    System.out.println("one"=="one");   //true
```

## !=

'!'는 부정을 의미한다. '같다'의 부정은 '같지 않다'이다. 이것을 기호로는 '!='로 표시한다. 아래의 결과는 !=의 결과인데 ==와 정반대의 결과를 보여준다. 

```java
    System.out.println(1!=2);           //true
    System.out.println(1!=1);           //false
    System.out.println("one"!="two");   //true  
    System.out.println("one"!="one");   //false
```

## >

좌항이 우항보다 크다면 참, 그렇지 않다면 거짓임을 알려주는 연산자다.

```java
    System.out.println(10>20);       //false
    System.out.println(10>2);            //true
    System.out.println(10>10);           //false
```

## >=
좌항이 우항보다 크거나 같다. 

```java
    System.out.println(10 >= 20); // false
    System.out.println(10 >= 2); // true
    System.out.println(10 >= 10); // true
```

## .equals

.equals는 문자열을 비교할 때 사용하는 메소드다. 우리는 아직 메소드를 배우지 않았기 때문에 지금은 그냥 이것을 연산자로 이해해도 무방하다. 

```java
    String a = "Hello world";
    String b = new String("Hello world");
    System.out.println(a==b);
    System.out.println(a.equals(b));
```