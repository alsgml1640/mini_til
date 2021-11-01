# CSS : 위에서 아래로 흐르는

1. css를 추가하는 방법
2. display 의 특징
3. box의 특징
4. Collapsing margin (마진상쇄)
5. 스타일 적용시
6. flex box
7. position
8. 셀렉터 (combinator)
9. 의사(가상) 요소 - ( pseudo element) -- 수정
10. 의사(가상) 클래스 ( pseudo selectors) - States -- 수정
11. 트랜지션

## css를 추가하는 방법

1. 같은 html 파일에 추가 : inline css
   > `<head>`태그에 `<style></style>`을 넣는다
2. css와 html파일을 분리 : External
   > `<link href="style.css" rel="stylesheet">`

- box - 박스(block) : 옆에 다른 요소가 못온다
  예시) div, p
- 박스가 아닌것 (inline) : 옆에 다른 요소가 올 수 있다.
  예시) a, span

  ![image](https://media.vlpt.us/images/eunsonny/post/e7ff3081-ded6-4c35-b2bd-f9d679a1d0f2/blockinline.png)

- `display : block`를 가진 요소를 `inline`으로 바꾸고싶으면 `display : inline`
- `display : inline`을 가진 요소를 `block`으로 바꾸고싶으면 `display : block`

```
• Inline의 특징
  : 높이와 너비가 없다
  : padding 은 적용된다
  : margin은 좌우만 된다. (위 아래에 마진을 가질수 없다 )
  : 만약 위 아래 마진을 가지고싶으면 display를 block으로 변경해야함
  : div의 display를 inline으로 바꾸면 화면에서 보이지않는다.
```

## display 의 특징

    - block은 높이, 너비가 있지만
    - inline은 높이와 너비가 없다.

## box의 특징

![box예시](https://media.vlpt.us/images/woals3000/post/c06b9ea3-38dc-4c8a-b391-3f06c61e2b73/box-model.png)

    - margin : border 경계의 바깥에 있는 공간
    - padding : border 경계의 안에 있는 공간
    - border : box 경계선 ,테두리
        박스의 경계
        솔직히 보더는 잘 안쓴다 (한종류만 쓴다 solid)
        Box ,inline 과 다 적용된다

## ! Collapsing margin (마진상쇄)

    흔히 `마진 겹침 현상` 이라고 부름
    박스끼리의 경계가 겹치면 그 두 박스의 마진은 하나로 겹쳐진다
    위 아래에서만 적용

---

### 스타일 적용시

    - id : 고유한 속성으로 하나만 선언 (#id)
    - class : id랑 다르게 여러개에 선언될 수 있고 동시에 같은 스타일 적용가능 (.class)

![mainAxis](https://user-images.githubusercontent.com/50939886/139521048-1f774c29-9a47-4102-8b8a-87254a874db1.png)

- main axis 주축
- corss axis 교차축

## flex box

    자식 요소에는 어떤것도 적지않음
    부모요소에만 명시 `display : flex`
    - Justify-content : 주축에서 움직인다.
    -  Align-items : 교차축에 적용됨
    교차축에 있는 아이템들을 움직이게 한다
    결론적으로 둘다 축 변경이 가능하다
    (부모요소)
    - flex-wrap : wrap 설정시 전체 화면 변경시 자식요소의 고정된 너비를 유지하면서 변화됨
    - flex-direction 사용
    디폴트는 row(수평) , column(수직)

## position

### Fixed

     레이아웃보다는 위치를 아주조금 위로 , 아주조금 옮기고 싶을때 사용….???
     Position :fixed 를 설정해주면 그 박스는 화면에 그대로 고정되어있다
    전체 바디를 늘려도 그 자리 그대로
    Top, bottom , left, right 프로퍼티 하나만 수정해도 다른 박스랑 같은 선상에 있지않는다 .
    ( 다른 레이어 )
    이것을 사용하면 다른 레이어에 위치해 있을 것이다
    모든 것의 위에 있다.

### Static (디폴트)

    레이아웃이 박스를 처음 위치하는 곳에 두는 것

### Relative

    element가 처음 위치한 곳 기준으로 수정한다.
    보이는 첫 기준점이 정말 중요!
    Top, bottom , left, right 수정시 element가 처음 위치한 곳 기준으로 수정한다.

### Absolute

    가장 가까운 relative 부모를 기준으로 이동시켜준다.
    만약 찾지못하면 body 기준으로 옮겨질것이다.
    Top, bottom , left, right 수정시 가장 가까운 relative 부모를 기준으로 이동시켜준다.

## 셀렉터 (combinator)

    P span : p안의 자식들
    P > span : p 바로 아래 자식
    P + span : p 바로 다음에 오는 형제 span
    P ~ span : 형제와 형제 관계 , 꼭 바로 뒤에 올 필요없다.

```
!!!!!!!!!!!!!!여기 수정 들어가기
- 의사(가상) 요소 - ( pseudo element)
    선택자에 추가하는 키워드
    선택한 요소의 일부분에만 스타일을 입힐수 있다
    예시 ) ::first-line ,:: placeholder ….
    :: placeholder - Placeholer 를 스타일하고싶을때
    :: selection - 드래그
    :: first-letter

- 의사(가상) 클래스 ( pseudo selectors) - States
    선택자에 추가하는 키워드
    의사 요소와 달리 요소의 특정 상태에 스타일 적용할 때
    예시 ): hover , : focus , : active , :visited 등등 ….
    필수 입력 대상이 아닌(required) input 요소를 선택자로 사용한다.
```

## transition (트랜지션)

- 요소의 속성을 서서의 다른 상태로 변화하는 애니메이션을 만드는 방법
- state (ex. :hover , :active ...)가 없는 요소에 붙는게 좋다
- transition은 state에 따라 바뀌는 property를 갖고 있으면 사용된다
- 트랜지션은 뿌리(:root)에 선언한다.
- 액션을 나눠서 주려면 콤마를 이용해서 따로 준다.

    <!-- 예시-->
    <head>
    <style>
      body {
        display: flex;
        height: 100vh;
        justify-content: center;
        align-items: center;
        }
      div {
        width: 300px;
        height: 300px;
        background-color: teal;
        transition: background-color 2s ease-in-out;
        }
      div:hover {
        background-color: aquamarine;
        opacity: 0.5;
        }
    </style>

    </head>
    <body>
      <div></div>
    </body>

###### 🧠 출처 : 노마드코더 - 코코아톡 클론코딩 css 이론 정리
