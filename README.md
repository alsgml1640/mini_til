# mini_til 💪💪💪💪💪

## 미니의 Today I Learned 🧠

    하루하루 공부한 내역을 간단하게 기록
    점점 발전하는 내가 되길.....🙏🙏🙏🙏

    -- 아직 수정할 내역이 많다는 것이 함정 ...

---

#### html,css 정리 내역

- [html 파트 정리 내용](https://github.com/alsgml1640/mini_til/blob/2fa34bd494f60045a9897fe4d8d253c663301369/Html/README.md)

- [css 파트 정리 내용 ](https://github.com/alsgml1640/mini_til/blob/08f9951030d533140c81970ac69f3689843ba7fa/Css/README.md)

# history

- [2022년 02월](#2022년-2월)
- [2022년 01월](#2022년-1월)
- [2021년 12월](#2021년-12월)
- 2021년 11월 - 추가 예정
- 2021년 10월 - 추가 예정

---

# 2022년 2월

# 🗓️ 2022.02.18

## 자바스크립트 - momentum 클론코딩(노마드)

### 한 일

**노마드코더 자바스크립트 마지막 미션 수행 (진행중) 1일차**

1. html 기본 뼈대 작성
2. css 파일 모듈화 작업
3. 배경화면 랜덤으로 지정

### 배운 것(복습한 것)

- 시맨틱 태그 (header , main , section , footer ...)
  - [참고 링크](https://velog.io/@gil0127/Semantic-Tag-정리)
- Flex 에 대한 재복습
  - [참고 링크](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
  - 메인 축(main)과 교차 축(cross)의 차이
  - justify-content , align-items 의 활용법

### 개선할 점 및 느낀 점

- 오랫만에 css를 하니까 많이 헷갈렸다 . 이번 미션을 수행하면서 자바스크립트에 대한 문법도 다시 익히고 그동안 잠깐 쉬었던 css 연습도 열심히 해야겠다.

&nbsp;

---

&nbsp;

# 🗓️ 2022.02.17

## 자바스크립트

- 노마드코더 - Todo-List 관련 및 챌린지
- 유데미 - 클린코드 자바스크립트 강의

### 한 일

1. 노마드 강의 - To-do List Part 나머지 강의 듣기
2. 챌린지 미션 수행 - Math.Random()을 사용하여 배경색 변경

   배경화면 가운데 버튼 클릭시 랜덤으로 background 의 color 가 변경되는 코드 작성

3. 노마드 강의 - 날씨 part 완강
4. 유데미 클린코드 자바스크립트 강의 시청 (섹션 2 : 6강까지 완료)

### 배운 것

**노마드 코더 관련**

- localStorage 에 담긴 해당 배열 삭제
  localStorage에서 지우고 싶은 데이터를 진짜로 지우는게 아닌
  지우고 싶은 item을 빼고 새로운 array를 만든다.

  ```jsx
  // 투두리스트 담을 배열
  let toDos = [];
  ****
  // 3. 삭제 후, 새로고침시 localStorage에 있는 데이터가 사라지지않아
  // 그대로 todo_List에 나오는거 수정
  function saveToDos(){
  	localStorage.setItem("toDos", JSON.stringify(toDos));
  	// localStorage.setItem(KEY, VALUE);
  }

  // filter 함수를 사용
  function deleteTodo(event){
  	const li = event.target.parentElement;
  	li.remove();

  	// 삭제하고 싶은 데이터의 id를 가져와 동일하지않으면
  	// 배열에 새로 filter를 거쳐서 넣어줌

  	// 4. 데이터 삭제시 localStorage에도 삭제하는 법 (업데이트)
  	toDos = toDos.filter((toDo) => toDo.id !== parseInt(li.id));

  	// toDos 배열을 다시 localStorage에 저장해줌
  	saveToDos();
  }
  ```

- filter 함수

  ```jsx
  // array의 1000 이상 제외한 요소를 새로 담아보자
  const arr = [1234, 5454, 223, 122, 45, 6775, 334];

  function sexyFilter(num) {
    num <= 1000;
  }

  arr.filter(sexyFilter);
  // 결과값 : [223, 122, 34, 334]
  ```

  ```jsx
  // todos 배열에 지정한 객체를 삭제해보자
  const todos = [{ text: "lalala" }, { text: "lololo" }];

  function sexyFilter(todo) {
    return todo.text !== "lololo";
  }

  todos.filter(sexyFilter);
  // 0: {text: 'lalala'}
  // length : 1
  // text : "lololo" 걸러진 채로 나온다.
  ```

- navigator , geolocation - 날씨 관련 (user의 위치 (geolocation))

  1. 위도와 경도를 알기

     ```jsx
     function onGeoOk(position) {
       // 위도 , 경도
       const lat = position.coords.latitude;
       const lng = position.coords.longitude;
       console.log(lat, lng);
     }
     ```

  2. ‘1’에서 알게된 위치로 장소로 바꿔줄 서비스를 사용해야 함
  3. [openweathermap.org](http://openweathermap.org) → 우리 위치의 날씨를 알려줄 것임

     navigator.geolocation.getCurrentPosition()

  4. **fetch !!!!**

### 느낀 점

Todo List 에서 데이터를 삭제할 때 해당 데이터의 ( Date.now()로 저장된 ) id를 가져와 해당 로컬 스토리지에서 삭제한다는 점이 너무 신기했다.

일단 전부 다 이해가 되는 상황은 아니지만 내일 남은 미션 수행을 하면서 다시 복습 과정을 거쳐야겠다.

### 개선할 점

- filter 함수 밑 Array 배열 안에 포함된 여러 기능들 정리하기
- weather 파트 부분 강의 다시 듣기
- fetch 개념에 대한 정리하기

&nbsp;
&nbsp;

# 🗓️ 2022.02.16

## 자바스크립트 - Todo-List 관련

### 한 일

1. 노마드 js 강의 - Todo_List 부분 강의 듣기 (7.4 ~ 7.6)

### 배운 것

- localStorage를 이용하여 to-do list 를 만드는법

  ```jsx
  const todoForm = document.getElementById("todo-form");
  const toDoInput = todoForm.querySelector("input");
  const todoList = document.getElementById("todo-list");

  // 투두리스트 배열
  const toDos = [];

  // 입력한 투두리스트를 localStorage에 저장하는 함수
  function saveToDos() {
    localStorage.setItem("toDos", JSON.stringify(toDos));
  }

  // 1. 입력한 데이터를 to do List 배열에 넣기
  // 입력칸에 엔터키 입력시 (핸들링 함수)

  function handleTodoSubmit(event) {
    event.preventDefault();
    const newTodo = toDoInput.value;

    // 랜덤으로 id를 생성하는 법
    const newTodoObj = {
      text: newTodo,
      id: Date.now(),
    };
    toDos.push(newTodoObj);
  }

  // 2. 새로고침 시 앞 전에 입력한 데이터를 기존 todo_list 배열에 넣기
  const savedToDos = localStorage.getItem(TODOS_KEY);

  // 저장된 투두리스트가 존재할 시 화면에 그리기
  if (savedToDos) {
    const parsedToDos = JSON.parse(savedToDos);
    toDos = parsedToDos;
    parsedToDos.forEach(paintTodo);
  }
  ```

- 랜덤으로 id 만드는 방법

  ```jsx
  // 1. Date.now()
  // 밀리초(1000분의 1초)를 주는 함수

  // 랜덤으로 id를 생성하는 법 - 객체로 생성
  const newTodoObj = {
    text: newTodo,
    id: Date.now(),
  };
  ```

### 느낀 점

노마드 강의를 들으면서 밑에 댓글창을 확인하는게 확실히 갈수록 댓글의 수가 줄어드는 것을 볼수 있다....

하하... 하지만 나는 완강을 해야지!!!

자바스크립트는 공부할수록 너무 어려운 거 같다.

&nbsp;
&nbsp;

---

&nbsp;

# 🗓️ 2022.02.15

## 자바스크립트 - Todo-List 관련

### 한 일

1. 노마드 코더 챌린지 - 7 (앞전 챌린지 실패로 인한 재도전) - 진행완료
2. 노마드 js 강의 - 3강 듣기 (to do list 부분)

### 배운 것

- **JSON.stringify**
  javaScript object나 array 또는 어떤 javascript 코드건 간에 string 으로 바꿔주는 기능
  ```jsx
  const player = { name: "mini" };
  JSON.stringify(player);
  // 결과 : '{"name":"mini"}'
  ```
- **JSON.parse**
  JSON 문자열의 구문을 분석하고 그 결과에서 Javascript값이나 객체로 변환

### 개선할 점

TodoList 파트를 완강한 후에 **JSON** 구조에 대해 좀 더 알아보기

&nbsp;

---

# 🗓️ 2022.02.14

## 1. 자바스크립트

### 한 일

노마드 코더 챌린지 - 7 (앞전 챌린지 실패로 인한 재도전) - 진행 중

### 느낀 점

2주정도 공부를 쉬었다고 금새 다 까먹은 느낌이다....

하하하 막막하다 .,,,

### 개선할 점

- 그냥 다......

## 2. GIT - CLI 관련

### 한 일

CLI 를 이용하여 깃허브에 업로드하는 법을 알기

### 배운 것

- 터미널에서 명령어를 입력하여 새로 추가한 파일을 깃허브에 푸시하는 과정까지의 명령어를 배웠다.

```powershell
1. 추가하기
$ git add .(현재 폴더에 있는 모든 파일)
$ git add 추가할 파일명

2. commit 하기
$ git commit -m "메시지 입력"

3. push 하기
$ git push origin main

```

### 느낀 점과 개선할 점

GUI로 주로 사용했는데 아무래도 실무에서는 CLI을 사용할줄 아는게 훨씬 좋을거니까 하나하나 다시 시도를 해보았는데 역시 헷갈린다 ..ㅠ

테스트용으로 하나 레포지토리를 파서 연습해야겠다.

&nbsp;

---

# 🗓️ 2022.02.01 - 02.13

### 수술 및 입원 , 퇴원 후 컨디션 난조로 인한 부재

---

&nbsp;&nbsp;

# 2022년 1월

# 🗓️ 2022.01.30

## 알고리즘 - 병합 , 최빈값

### 한 일

유데미에서 자바스크립트를 이용한 기초 알고리즘 강의에서 병합과 최빈값을 구하는 강의를 들었다

# 🗓️ 2022.01.28

## 1. 자바스크립트 - [틱택토 게임 만들기](https://www.notion.so/e216a6c76b8f45d2a0683194abe50839)

### 한 일

틱택토를 만드는 강의를 들으며 클론 코딩을 하였다.

### 배운 것(새로 알게된 것)

- 이차원 배열
- 구조 분해 할당
  ```jsx
  // 둘다 같은 뜻
  const { body } = document;
  const body = document.body;
  ```
- 이벤트 버블링, 캡처링
  - 리무브 이벤트 리스너는 언제 사용하면 좋은 것인가 ?
    - 게임 자체가 완전히 끝날때 ?!

### 느낀 점

기본 배열도 이제 겨우 알듯한데 이차원 배열이라니.....허허

전반적으로 강의를 듣고 일단 클론코딩을 한 다음 다시 재복습을 해야겠다

당장 이해할라고 하면 시간이 너무 많이 걸릴 듯 하다 ...

## 2. 구조 분해 할당 (destructuring)

### 한 일

틱택토 강의를 들으면서도 구조분해 할당에 대한 이해가 되지 않아서

구글링 및 딥다이브 js를 보면서 구조분해할당 (36장)에 대해 읽어보았다.

### 느낀 점

.....??? 온갖 구글링을 하면서 코드도 따라 쳐봤지만 수박 겉핥기도 안되는 느낌이다....

이런... 복습만이 살길!!!

# 🗓️ 2022.01.26

## 자바스크립트 - [반응 속도 체크](https://www.notion.so/1-782c5f7cd69146aabf0ae41407399dba)

### 한 일

1. 반응속도들의 평균을 구하였다.
2. 빨간 화면일 때 클릭하면 성급한 행동이라는 것을 알리는 코드를 작성했다.
3. 반응 속도 체크하는 코드를 강의를 안보고 스스로 해보았다.

### 배운 것

- 배열과 객체의 차이점에 대해
- reduce() - 배열 메서드 (누적값) , 배열을 조작할때 가장 강력한 메서드 중 하나

  ```jsx
  // reduce((a,c) ⇒ { (a+c) , [초기값 : 지정안하면 첫번째 요소값]})
  // a는 누적값 , c는 현재값
  [1,2,3,4].reduce((a,c)=> (a+c));
  // a : 1 , c : 2
  // a : 3 , c : 3
  // a : 6 , c : 4
  // (return값) 10

  // 객체식으로도 표현가능하다
  ['가','나','다','라'].reduce((a,c,i) => { a[i] = c ; return a }, {})
  {0: '가', 1: '나', 2: '다', 3: '라'}

  //{0: '가'} '가' , i:0
  //{0: '가', 1: '나'} '나', i:1
  //{0: '가', 1: '나', 2: '다'} '다' i:2
  //{0: '가', 1: '나', 2: '다', 3: '라'} '라' i:3
  ```

### 느낀 점

아직 append()와 appendChild()의 구분이 아직 어렵다.... ㅠㅠㅠㅠ

저번 로또 게임만들때도 사용해보았지만 다시하려니 헷갈리구나...

역시 프로그래밍은 계속 반복반복!!!!

### 개선할 점

- 배열과 객체의 차이점에 대해 좀 더 고민을 해보아야겠다.
- append() 와 appendChild() 에 차이에 대해 더 공부하기
- reduce() 메서드에 대한 개념 다시 정리

---

# 🗓️ 2022.01.25

## 자바스크립트 - [반응 속도 체크](https://www.notion.so/1-782c5f7cd69146aabf0ae41407399dba)

### 한 일

반응 속도 강의를 듣고 순서도 그리기를 해보았다

강의를 보고 클론 코딩하면서 화면 클릭 후 화면 전환이 되는 시간
즉, 반응속도를 측정하였다.

머릿속에 남은 지식을 바탕으로 다시 혼자 반응 속도 게임을 만들어 봤다. (셀프체크)

### 배운 것

- 비동기 - 이벤트 리스너와 타이머는 비동기이다
- Date()
- ClassList , ClassName
  ```jsx
  // classList 사용법
  태그.classList.add("클래스"); // 추가
  태그.classList.replace("기존클래스", "수정클래스"); // 수정
  태그.classList.remove("클래스"); // 제거
  ```
- cleatTimeout() - setTimeout을 실행하지 않게한다.

  ```jsx
  let timer = setTimeout(() => {
    startTime = new Date();
    $screen.classList.remove("ready");
    $screen.classList.add("now");
    $screen.textContent = "클릭하세요!";
  }, 1000);

  clearTimeout(timer);
  ```

### 느낀 점

비동기는 아직 어렵다... 좀더 반복해서 내껏으로 만들도록 하자

---

# 🗓️ 2022.01.22

## 검색 알고리즘

### 한일

검색 알고리즘에 대한 강의를 다시 복습하고 실습을 해보았다.

이진 검색을 이용한 코드 정리를 해보았다.

### 배운 것

- 정렬된 배열에서 원하는 값을 찾는 프로세스 → 그중에 찾을 값을 정하기
- 이진 검색

### 느낀 점

알고리즘은.... 정말 많은 시간을 투자해야 할 거 같다는 생각이 든다......

### 정리 내용

- [검색 알고리즘 (이진검색)](https://www.notion.so/efc8c79a79a74db499e816e8f30b8d24)

# 🗓️ 2022.01.21

## 1. 검색 알고리즘

### 한 일

검색 알고리즘에 대한 강의를 들었다.

### 배운 것

- 검색 알고리즘은 배열 등의 데이터에서 특정 값을 검색하는 알고리즘이다.
- 일반적으로 순차 검색과 이진 검색 등으로 구분

### 느낀 점

순차검색보다는 이진검색이 낫고 대신에 이진 검색은 처음부터 정렬이 올바르게 되어있어야한다는점 ???

## 2. 자바스크립트 - 크롬 클론코딩 (노마드)

### 한 일

자바스크립트 파일내에서 생성한 무언가를 html에 추가하기

### 배운 것

- createElement()
- appendChild() , append()

### 느낀 점

appendChild() 와 append() 의 구분이 아직은.,... 헷갈린다.

### 내용 정리

- [appendChild() 와 append() 의 차이](https://www.notion.so/appendChild-append-c249561142d245d380fcfd003834ff67)
- [createElement()](https://www.notion.so/createElement-a09997c683b348a99ec9e55bd8b2e178)

---

# 🗓️ 2022.01.19

## 자바스크립트 - 크롬 클론 코딩 (노마드)

### 한 일

노마드 챌린지 8 과제를 진행하였다.

: _Date 와 setInterval 함수들을 사용해 크리스마스까지 며칠이 남았는지 알려주는 시계를 만들어라_

### 배운 것

- date 객체를 이용하여 현재 시간 및 지정한 날짜를 표현할 수 있다.
- setinterval()과 setTimeout()의 공통점을 알 수 있다.
- padStart() 와 padEnd() - string에 사용 가능
  : string에 space 간격을 지정

### 느낀 점

date객체를 이용하여 날짜,시,분,초 다양하게 표현할 수 있는 방법이 있다는 것을 알았고

.....일단 어렵다

생각보다 각자의 시,분,초를 구할 때 헷갈려서 열심히 구글링을 한 결과 챌린지 과제는 수행할 수 있었다.

### 내용 정리

- [date()](https://www.notion.so/Date-cb459e5655ae4515b4302b9f691edfea)

---

# 🗓️ 2022.01.17

## 자바스크립트 - 크롬 클론 코딩

### 한 일

1. form 태그에 preventDefault() 이벤트를 넣어 form의 기본동작인 submit동작을 막았다.
2. 이 object에는 방금 일어난 event에 대한 여러 정보가 담겨있다.

### 배운 것

- preventDefault() - 어떠한 이벤트의 기본 행동이든지 발생되지 않도록 막는 것
- local Storage (로컬 스토리지)
- 브라우저는 브라우저 내에서 event로 부터 정보를 잡아내서 실행을 하도록 하게 설정
- form의 기본 동작 : submit
- a(link)의 기본 동작 : click

### 느낀 점

미루지말고 자바스크립트 강의 완주를 하자!!!

### 정리 내용

- [로컬 스토리지 (Local Storage)](https://www.notion.so/Local-Storage-ee38cffc279c45f6a3c52797269cc85c)

---

# 🗓️ 2022.01.14

## 1. 알고리즘 - 순위 , 정렬

### 한 일

1. **순위 알고리즘**에 대한 강의를 들었다.
2. 정렬 알고리즘은 헷갈려서 다시 한번 더 들었다.

### 배운 것

- 순위 알고리즘 (rank)
- 정렬 알고리즘

### 느낀 점

- 순위 알고리즘에서 생각보다 시간을 많이 잡아먹었지만 뭔가 뿌듯...???
  집중력있게 더 몰입하자!!!

### 개선할 점

- 순위 알고리즘에서 1등순대로 나열하는 로직을 짜도록 하자

### 정리 내용

- [순위 알고리즘 (rank)](https://www.notion.so/rank-8435056b67dd42a1892e33987824a83a)
- [정렬 알고리즘 (sort)](https://www.notion.so/sort-selection-29ad52784c284e8e88df0d0ce64d2103)

## 2. 노마드 챌린지 - javascript

### 한일

노마드 코더에서 자바스크립트를 이용한 크롬 클론코딩 강의를 들었다,

### 배운 점

- [window](https://developer.mozilla.org/ko/docs/Web/API/Window) : window 인터페이스는 Dom 문서를 담을 창
- resize : document view의 크기가 변경될 때 발생
- 자바스크립트 윈도우창의 크기조절
  ```jsx
  window.addEventListener("resize", function () {
    console.log("Resizing....");
  });
  ```

### 느낀 점

노마드 강의는 훅훅 진도가 나가서 좋다 .... 그리고 재밌다...

---

# 🗓️ 2022.01.12

## 알고리즘

### 한 일

**정렬 알고리즘**에 대한 강의를 들었다

### 배운 것

- 정렬 알고리즘은 주어진 범위 내에서 불규칙적으로 나열된 순서를 일정 기준에 따라 순서대로 나열하는 알고리즘
  - 선택 정렬(selection) , 버블 정렬(bubble) , 퀵 정렬

### 느낀 점

여기서부터 뭔가 점점 헷갈리기 시작했다......

선택 정렬이고 버블이고 둘다 비슷한거같은데.......

---

# 🗓️ 2022.01.11

## 알고리즘

### 한 일

최대값, 최소값 알고리즘 강의를 들었다

### 배운 것

- IIFE (즉시실행함수) 표현에 대해 알았다 → (function(){})()
- **`Number.MIN_SAFE_INTEGER` 와 `Number.MAX_SAFE_INTEGER` 상수는 JavaScript에서 안전한 최소 / 대 정수값을 나타낸다.**

### 느낀 점

의욕아 솟아라....!!!!

### 정리 내용

- [최대값 알고리즘](https://www.notion.so/max-ca9bec81f4f341c19e83467b07bcc44b)
- [최소값 알고리즘](https://www.notion.so/min-48104c3722b547108f1a767aef41f6be)

---

# 🗓️ 2022.01.07

## 알고리즘

### 한 일

**합계, 등차, 평균** 알고리즘 강의를 듣고 실습 및 복습을 하였다.

### 배운 것

- index없이 콘솔에서 결과를 실행하기
  ```powershell
  **node [실행할 js 파일명.js]**
  ```
- Array() 사용법에 하여 순차적으로 정렬된 배열을 선언할수 있다
- Array() 배열 선언시 Array(n) 으로 선언하면 길이가 n인 배열이 선언된다.
- for문을 forEach문으로 변형시킬수 있다.

### 느낀 점

- 아직 완전 기초 알고리즘이라 그런가 아직까진 엄청 어렵다는 생각은 안든다....
  하지만 나중에 이거 강의 한바퀴돌고 프로그래머스에 입문하려면 지금 이건,......
  아무것도 아니겠지????

### 정리 내용

- [합계 알고리즘 (sum)](https://www.notion.so/sum-2beb670317d945c5965cca661c757db6)
- [등차수열 알고리즘 (Arithmetic)](https://www.notion.so/Arithmetic-ea63da3c850b4610964938e75c85b47d)
- [개수 알고리즘 (count)](https://www.notion.so/count-0f72ee25cb934a73b5caeffb01e0a682)

---

# 🗓️ 2022.01.05

## 1. 알고리즘

### 한일

1. 알고리즘 기초 강의를 듣고 기본적인 알고리즘 시스템에 대해 강의 및 실습을 해보았다.

### 배운 것

- 프로그램이 가장 작은 단위는 일반적으로 입력 → 처리 → 출력 의 단계를 거친다.
- 여기서 처리 단계가 알고리즘으로 보면 된다.

1. 입력(input) : 자료 구조(data Structure)가 담당하는 영역
   - 간단히는 변수 및 배열의 데이터가 사용되고 더 나아가 컬렉션, 파일, db의 데이터가 사용되는 영역
2. **처리(process) : 알고리즘 영역**
3. 출력(output) : ui가 담당하는 영역, 일반적으로 콘솔, 데스크톱, 웹, 모바일 등의 영역으로 나뉘어 가공된 데이터가 출력

- 난이도
  | 난이도 | 알고리즘 | 사용 유형 |
  | ------------------------------ | ------------------------------- | ------------------------------------------- |
  | 초급 | 합계(sum) | 합계 출력 |
  | | 개수(count; 횟수, 건수) | 자료 건수 출력 |
  | | 평균(AVERAGE) | 평균을 출력 |
  | | 최댓값(MAX) | 최댓값을 출력 |
  | | 최솟값(MIN) | 최솟값을 출력 |
  | 중급 | 최댓(소)값 → 최솟(대)값 | ~에 대해 최댓(소)값을 구하되, 동일값 발생시 |
  | ~에 대해 최솟(대)값을 구하시오 |
  | | 최대(소)값 → 최대(소)값 | ~에 대해 최대(소)값을 구하되, 동일값 발생시 |
  | ~에 대해 최대(소)값을 구하시오 |
  | 고급 | 근삿값(NEAR) | ~에 가까운 값을 구하시오 |
  | | 순위(RANK) | 순위를 구하시오 |
  | | 정렬(SORT) : 오름차순, 내림차순 | 오름(내림)차순을 정렬하시오 |
  | | 검색(SEARCH) | 특정 자료를 검색하시오 |
  | | 병합(MERGE) | 2개의 배열을 하나의 배열로 합치시오 |
  | | 최빈값(mode) | 가장 빈도수가 높은 자료를 구하시오 |
  | | 그룹(group) | 특정 항목별 그룹화하여 소계를 구하시오 |

### 느낀 점

알고리즘은 오늘 처음 들어서 아직은..... 할만한거같다

자주는 아니더라도 조금씩 알고리즘 공부도 시작해야겠다

## 2. [가위바위보 게임](https://www.notion.so/022af55676c54b0883a3790938a53567)

### 한 일

제로초님의 자바스크립트 강의에서 가위바위보 만드는 부분을 시청했다.

### 배운 것

- 가위바위보에 대한 순서도
- [~~객체~~](https://www.notion.so/object-aa127fdc15c94b7eb9af7a73dade4a56)

### 느낀 점

순서도를 늘 미리 먼저 그려보라고 하신다

아직도 순서도 그리는 것은 헷갈리고 어렵다....

---

# 🗓️ 2022.01.04

## 1. [Cypress](https://www.notion.so/Cypress-3df3f17e3cdc47458351faaa44c948fc)

### 한일

1. Cypress 강의 시청을 하여 test Code 작성 법을 보았다.

### 배운 것

- cypress 설치하는 법
  ```powershell
  1. npm init
  2. npm install cypress --save-dev
  ```
- Cypress 실행법
  ```powershell
  npx cypress open
  ```

### 느낀 점

개발자가 일일이 테스트하는 시간을 테스트코드를 이용하면 시간을 10초 내외로 끝낼수 있다는 것이 너무 신기했고 아직 cypress 홈페이지가 익숙하지 않아서 조금씩 테스트코드를 작성하면서 홈페이지에 나와있는 cypress 사용법에 익숙해져야겠다.

## 2. 로또 추첨 게임 만들기

### 한일

배열을 이용하여 로또 추첨하는 게임을 만들기

### 배운 것

- 타이머 기능 [(setTimeout , setInterval)](https://www.notion.so/setTimeout-setInterval-e4988704829845cbad9524d8accdfb59)
- [Array() 배열](https://www.notion.so/Array-ex-splice-slice-27100589a943489ca5b24723e6bf339b)
- [블록 스코프, 함수 스코프](https://www.notion.so/eecba7eade3e47ebacbf753aac9dc586)
- [클로저](https://www.notion.so/10e90d4cc0de4e9b8dc3c0794cfec65a)
- [비동기](https://www.notion.so/e49f6a473eec49dca6925af2e2d17c0e)

### 개선할 점

1. 비동기에 대한 이론이 아직 제대로 이해가 되지 않는다 .
2. setTimeout, setInterval 활용에 대해 좀 더 실습을 해봐야겠다.
3. 클로저는 솔직히 지금 당장 이해는 안되어서 자바스크립트 기초를 어느정도 뗀다음에 다시 회독 해야겠다

---

# 2021년 12월

# 🗓️ 2021.12.30

## 자바스크립트 - 로또

### 한 일

로또 만들기 게임 강의를 보면서 클론 코딩을 하였다.

### 배운 것

- Array() 배열 및 Array 메서드 함수 (slice, splice, )
- Math.random()
- sort() - 배열안의 요소들을 오름차순 및 내림차순으로 정렬해주는 메서드

### 느낀 점

스코프와 비동기 및 클로저의 중요성을 강조하셨는데 일단 ,,,,, 너무 어려우니 일단은 패스

다음 회독때 다시 좀더 깊게 들어가기

일단은 전체적으로 한번 훑고 돌아오기

### 개선할 점

- 생성한 공안에 색상을 입히기

### 정리 내용

- [로또 만들기](https://www.notion.so/279cd81460d045678b402abb91761b1a)
- [Math 함수 관련](https://www.notion.so/Math-1e9f7089bbba4abdb09a1e640ce5a504)

---

# 🗓️ 2021.12.22

## 자바스크립트 - 숫자 야구 게임

### 한 일

랜덤 메서드(Math.random())를 이용하여 컴퓨터에서 무작위로 숫자를 제시하도록 하는 점

### 배운 것

- Math.random() 등 Math 함수
- ~~createTextNode()~~

### 개선할 점

1. 숫자를 랜덤으로 생성할 때 중복이 안되게 설정
2. append와 appendChild에 대한 이해

### 정리 내용

- [숫자 야구 게임 정리](https://www.notion.so/71e9e9a5490c4e1fb5f060da9bd83f32)

---

# 🗓️ 2021.12.15 ~ 16

## 자바스크립트 - 계산기 만들기

### 한 일

js를 이용하여 계산기 기능을 구현하였다.

### 배운 것

- ~~고차함수 (high order function) - 함수를 인자로 받거나 또는 함수를 반환함으로써 작동하는 함수
  간단히 말해 고차함수는 함수를 인자로 받거나 함수를 출력(ourput)으로 반환하는 return 함수를 말한다.~~
  예시 ) map, filter, reduce
- 중첩if문
  1. 공통된 절차를 각 분기점 내부에 넣는다
  2. 분기점에서 짧은 절차부터 실행하게 if문을 작성한다
  3. 짧은 절차가 끝나면 return이나 break로 중단
  4. 남은 else 제거

### 느낀 점

원래는... 오전에 하려고했는데 운동갔다가 자는 바람에 ..... 결국 오후에 하고말았다.

컨디션 조절에 좀더 신경쓰자!!!!

생각이상으로 예외처리를 많이 해줘야한다는 점

### 개선할 점

고차함수에 대한 정보를 더 찾아보기

### 정리 내용

- [계산기 만들기](https://www.notion.so/f4fdb516205e4907a8ff8f68136f22fe)
- [map() , filter(), reduce()](https://www.notion.so/map-filter-reduce-371a1303224a44e1bba7c36d7b300155)

---

# 🗓️ 2021.12.10

## 별 찍기

### 한 일

순서도의 중요성을 알았다.

크롬상의 개발자 모드를 이용하여 콘솔창에 별을 찍어보았다.

### 배운 것

- repeat() - 문자열을 반복한 값을 반환하는 메서드
  ```jsx
  console.log("2".repeat(3));
  // 222
  ```
- ~~배열의 기본 - pop(), push() , splice() , indexOd() , lastIndexOf()~~

### 느낀 점

다시 자바스크립트 기초공부를 하면서 솔직히 이정도는 껌인줄알았지만 ....

생각보다 복잡하구나.....

### 개선한 점

순서도에 대한 고민을 더 많이 해야할거같다.

### 정리 내용

- [별찍기 (콘솔)](https://mini1122.tistory.com/42?category=986291)

---

# 🗓️ 2021.12.08

## 넥스트스텝 - 클린코드 스터디 : 로또 미션

### 한 일

코드 모듈화 정리

싸이 프레스 테스트 작업 진행

### 느낀 점

넥스트스텝 과정은 솔직히..... 나한테 너무 무리였다......

ㅜㅜㅜㅜ 역시나,,, 솔직히 조교님들 없었으면 진작에 망했을거같다.
