# JWT

## JWT란?

### JWT(Json Web Token)
> 정보를 비밀리에 전달하거나 인증할 떄 주로 사용하는 토큰으로,Json객체를 사용함

JWT는 Json Web Token의 약자로 일반적으로 클라이언트와 서버 상이에서 통신할 떄 권한을 위해 사용하는 토큰이다.웹 상에서 정보를 Json형태로 주고 받기 위해 표준규약에 따라 생성한 암호화된 토큰으로 복잡하고 읽을 수 없는 string 형태로 저장되어있다.


## JWT구성

aaaa.bbbb.cccc와 같이 세 파트로 나누어짐
각각 head,payload.signature로 구성됨

### Header
- 토큰의 타입과 해시 암호화 알고리즘으로 구성
    + 토큰유형(JWT)
    + 해시 알고리즘(HMAC,SHA256,RSA 등)

```json
{
  "typ": "JWT",
  "alg": "HS256"
}
```

### Payload

전달하려는 정보(ex. 유저 id,role 등): claim 이라고 부름
- key: value 형태로 전달

```json
{
  "iss": "//sso.tvcf.co.kr",
  "iat": 1626308465,
  "exp": 1626394865,
  "roles": [
    "guest",
    "user"
  ],
  "userId": "tonydev",
  "userName": "tony",
  "userType": 3,
  "userLevel": 1
}
```

#### 일반토큰 vs claim

- 일반토큰의 문제점
    + 발급된 토큰에 대해 만료를 시킬 수단이 없다.
    + 발급된 토큰을 검사하거나 처리할 때 마다 DB에 접근하여 검사할 경우 부담이 생긴다.
    + 사용자 로그아웃 등으로 인한 토큰을 관리할 수 있는 방법이 없다.

- 클레임(claim: 청구,요구)
    + 정보를 담고 있는 토큰
    + 클레임의 종류 3가지
        1. 등록된 클레임(Registered Claim)
            * 토큰 정보를 표현하기 위해 이미 정해진 데이터 종류, 선택적으로 작성 가능
            * iss : 토큰 발급자(issuer)
            * sub : 토큰 제목(subject)
            * aud : 토큰 대상자 (audience)
            * exp : 토큰의 만료 시간(expiration)
            * nbf : 토큰 활성 날짜(not before) - 이 날짜가 지나기 전 토큰은 활성화 되지 않음
            * iat : 토큰이 발급된 시간(issued at)
            * jti : JWT Id - 중복 방지를 위해 사용, 일회용 토큰(Access token 등)에 사용
            * 시간 관련 숫자 : NumericData 확인 방법
                - new Date(parseInt("1626394865") * 1000)
        2. 공개 클레임(Public Claim)
            * 충돌을 방지하기 위해서 공개된 이름
            * URL 형태로 작성
            * 예시 : { "https://hexlant.com": true }
        3. 비공개 클레임(Public Claim)
            * 실제 사용을하는 개발자가 지정, 서버와 클라이언트가 서로 정의하여 사용하는 클레임
            * {"token_type": "access"}





