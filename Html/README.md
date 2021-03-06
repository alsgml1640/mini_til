# < 이론 설명!!!!>

    - 브라우저는 인간들이 쓰는 언어를 이해못한다.( 멍청함)
    - 우리가 해야할일은 브라우저에게 콘텐츠가 무엇인지 알려줘야한다.

1. 폴더명은 항상 소문자!!
2. 파일명도 항상 소문자!!

### HTML (뼈대)

마크업 언어

    - 브라우저에게 웹사이트의 content가 무엇인지 , 어떻게 구성되어있는지 설명할때 사용
    - Html은 오류가 없다
    - 컨텐트가 무엇인지에 대해서 알려주는것

### CSS (근육)

    - 디자인과 스타일을 위한 언어
    - 브라우저에게 웹사이트가 어떻게 보여야하는지에 대해 알려줌 - 콘텐트들이 어떻게 보일까

### 자바스크립트 ( 뇌 )

    - 웹사이트를 동적으로 만들어주는 프로그래밍 언어

---

#### 확장 프로그램

    - Community Material Theme : 화면 배경
    - Material Icon theme : 보이는 아이콘
    - prettier : 태그 실수 및 라인이 안맞는것을 자동으로 수정해주는 확장 프로그램

### 태그( tag )

    - Html은 오류가 없으나 브라우저나 이해하는 실제 태그를 넣으면 작동이 된다.
    - 제대로 된 위치에 넣고 , 이 tag를 기억하면 브라우저는 지정한 태그에 맞춰 변경되어 보여준다.

### 리스트

    - Ul : unordered list ( 순서가 없는 )
    - Ol : ordered List ( 순서가 있는 )

### 태그의 속성 ( attributes)

    - 태그에 추가하는 부가적인 정보
    - img 태그는 따로 닫는 태그가 없다. 그 자체가 self-closing tag (자체 닫기 태그)
    - a 태그를 사용할때는 href 라는 속성을 붙여주어 화면이동을 할수 있게 도와준다
    - img는 인터넷에 올려져있는 이미지 또는 로컬 이미지를 사용할 수 있다 : 경로를 지정해주어야 한다.

> 링크를 만들기 위한 속성 : href , target
> 이미지 속성 : src

#### Html을 구성하는 형태

    - 첫번째는 무조건 < !DOCTYPE html >
    - 브라우저에게 text 파일이 아니라 html 문서라고 알려주는 것

#### 웹사이트의 구조는 두개의 태그로 구성

1. head

   - 웹사이트의 환경설정을 해주는 곳
   - 외부적으로 보여지지 않는 설정을 해줌
   - 이 태그에 속해있는 모든 태그들은 화면에선 안보인다.

2. body
   - 사용자가 볼 수 있는 content 를 보여줌
   - 브라우저 화면상에 보여질 내용들은 전부 바디태그안에 있어야함.
   - 태그를 작성하는 방법, 속성을 어떻게 찾는지 알고 그 속성을 어떻게 사용하는지 알면 괜찮다,

### Form

    - Label : for
    - Input : id

![예시](https://user-images.githubusercontent.com/50939886/138669464-efcac021-788f-413b-aeaa-578d4837b9dd.png)

    - 값이 같을 때 for 과 같은 값을 가진 id를 들고있는 input 작동시켜준다

### 중요!! - ID

    - 바디안에 어떤 캐그에든 넣을수 있는 attribute 이다.
    - 고유 식별자이기 때문에 요소당 하나의 아이디만 가질수 있다
    - 전체 html 문서에서 id값은 고유해야한다.
    - 스크립팅이나 css를 식별할려는 목적을 가짐

### 시멘틱 html (Semantic) : 의미가 있는 태그

    - document 와 content 를 명확하게 묘사할수 있도록
    - Header, main, footer 등등
    - 보는 사람과 웹사이트로 바로 태그의 의미를 파악하기가 더 쉽다
    - 사방팔방 div로 하기보단 명확하게 시멘틱 태그를 쓰는것도 좋은 방법이다 - Div는 단순 아무의미도 없는 박스 태그

## 총정리!!!!

    - html은 뼈대 - 브라우저가 이해할수 있는 언어
    - Css 는 근육
    - 자바스크립트 : 뇌
    - 코드만 보고 어떤 의미인지 파악하기 위해 시멘틱 태그를쓴다.

---

### Attribute 값에는 항상 큰 따옴표를 사용한다

### 어떤 속성은 모든 태그가 사용 가능하고

### 일부 속성은 일부 태그에만 사용 가능하다

###### 🧠 출처 : 노마드코더 - 코코아톡 클론코딩 이론 정리
