# CSS

cascading : 위에서 아래로 흐르는
브라우저가 코드를 읽을대 위에서 아래로 흐른다
만약 같은 상속자를 두고 스타일을 지정하면 마지막이 지정한 스타일이 적용

- css를 추가하는 방법

1. 같은 html 파일에 추가 : inline css
   > `<head>`태그에 `<style></style>`을 넣는다
2. css와 html파일을 분리 : External
   > `<link href="style.css" rel="stylesheet">`

- box - 박스(block) : 옆에 다른 요소가 못온다
  예시) div, p
- 박스가 아닌것 (inline) : 옆에 다른 요소가 올 수 있다.
  예시) a, span
  ![image](https://media.vlpt.us/images/eunsonny/post/e7ff3081-ded6-4c35-b2bd-f9d679a1d0f2/blockinline.png)

- display : `block`를 가진 요소를 `inline`으로 바꾸고싶으면 `display : inline`
- display : `inline`을 가진 요소를 `block`으로 바꾸고싶으면 `display : block`

```
	• Inline의 특징
	: 높이와 너비가 없다
	: padding 은 적용된다
	: margin은 좌우만 된다. (위 아래에 마진을 가질수 없다 )
	: 만약 위 아래 마진을 가지고싶으면 display를 block으로 변경해야함

```

## div의 display를 inline으로 바꾸면 화면에서 보이지않는다.

    - block은 높이, 너비가 있지만
    - inline은 높이와 너비가 없다.

## box의 특징

![box예시](https://media.vlpt.us/images/woals3000/post/c06b9ea3-38dc-4c8a-b391-3f06c61e2b73/box-model.png)

- margin : border 경계의 바깥에 있는 공간
- padding : border 경계의 안에 있는 공간
- border : box 경계선 ,테두리
  - 박스의 경계
  - 솔직히 보더는 잘 안쓴다 (한종류만 쓴다 solid)
  - Box ,inline 과 다 적용된다

### ! Collapsing margin (마진상쇄)

    흔히 `마진 겹침 현상` 이라고 부름
    박스끼리의 경계가 겹치면 그 두 박스의 마진은 하나로 겹쳐진다
    위 아래에서만 적용

---

### 스타일 적용시

    - id : 고유한 속성으로 하나만 선언 (#id)
    - class : id랑 다르게 여러개에 선언될 수 있고 동시에 같은 스타일 적용가능 (.class)

#### flex box

    - 추후에 업뎃예정!! ( )

###### 🧠 출처 : 노마드코더 - 코코아톡 클론코딩 css 이론 정리
