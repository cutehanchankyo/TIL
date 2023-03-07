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
1. Im-D/Dev-Docs에 들어가서 새로은 pull request를 만든 다.

2. pull request 작성시 제목은 커밋메세지의 뒤에 있는 내 용을 적어준다.

## Review 방법

내가 보고자 하는 PR을 들어가게 되면 상단에 FileCHanged를 클릭한다.

리뷰를 하고자 하는 line에 마우스를 올려놓게되면+버튼이 생기게 되고 클릭을 한다.

해당 라인에 대한 Comment를 남긴다.

우측 상단에 위치한 finish your review 를 클릭하여 자신의 리뷰를 등록한다.

등혹하게 되면 PR의 하위에 생성이된다. 또한 해당 리뷰에 Comment를 올릴 수 있어 소통이 가능하다.

반영이 완료가 되거나 끝난 리뷰는 해결 처리를 한다.

## Approve 방법

해당 PR에 대해서 `나는 승인을 했다`라는 의미를 부여한다.

File Changed에서 Approve를 선태하고 Comment를 날려주며 면 된다.
