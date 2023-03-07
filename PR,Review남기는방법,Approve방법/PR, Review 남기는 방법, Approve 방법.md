# PR, Review 남기는 방법, Approve 방법

## PR날리는 과정 살펴보기
기존:fork를 해서 PR을 날리는 방법
현재:Im-D/Dev-Docs를 clone받아서 처리하는 방법

## Repo 내려 받기
1. 자신이 원하는 위치로 이동한다.
2. git clone으로 해당 레포지토리를 내려받는다.

```
git colne {url주소}
```

## 서버에 커밋하기
1. 자신의 브랜치를 만든다.

2. 자신의 글을 맞는 폴더 위치에 만든다.

3. 글작성이 완료되면 `add .`,`commit`을 한다.

4. 서버에 `push` 한다.

`push`를 할 때는 자신의 현재 브랜치를 확인하고 섭버의 자신의 브랜치와 동일한 브랜치에`push`한다.

```
git push origin {Date}/{your_name}
// ex) git push origin 20230307/Jeongchangyo
```

## PR작성하기
