# 박소영
---
## 23.04.06 6주차 <img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=React&logoColor=white"/>
<br>

#### 참고교재 소플의 처음 만난 리액트

---
### 실습 <댓글 컴포넌트 만들기> <div><br>

Comment.jsx
```js
import React from "react";

function Comment(props){
  return (
    <div>
    <h1>제가 만든 첫 컴포넌트 입니다.</h1>
    </div>
  );
}

export default Comment;
```

CommentList.jsx
```js
import React from "react";
import Comment from "./Comment";

function CommentList(props){
  return (
    <div>
     <Comment/>
    </div>
  );
}

export default CommentList;
```

index.js
```js
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import CommentList from './chapter_05/Comment';

setInterval(() => {
  const root = ReactDOM.createRoot(document.getElementById('root'));
  root.render(
    <React.StrictMode>
    <CommentList />
    </React.StrictMode>
  );
}, 1000);

```



## 23.03.30 5주차 
<br>

#### 참고교재 소플의 처음 만난 리액트

---

## 엘리먼트
### 1. <mark>엘리먼트</mark>의 정의
~~~
 - 엘리먼트는 리액트 앱을 구성하는 요소를 의미
~~~
### 2. <mark>엘리먼트</mark> 의 생김새
~~~
- 리액트 엘리먼트는 자바스크립트 객체의 형태로 존재
- 컴포넌트(button등), 속성(color 등) 및 내부의 모든 chidren을 포함하는 일반 JS 객체
- 이 객체는 마음대로 변경할 수 없는 불변성을 갖고있다.
~~~
### 3. <mark>엘리먼트</mark> 의 특징
~~~
-리액트 엘리먼트의 가장 큰 특징은 불변성입니다.
-즉, 한번 생성된 엘리먼트의 chidren이나 속성(attributes)을 바꿀 수 없습니다.
~~~

### 4. 엘리먼트 렌더링하기 <br><br>

### 5. 랜더링 된 엘리먼트 업데이트하기

```
function tick(){
  const element = (
    <div>
    <h1>안녕 리액트<h1>
    <h2>현재 시간: {new Date().toLocaleTimeString()}</h2>
    </div>
  );

  ReactDom.render(element, document.getElementById('root'));
}

setInterval(tick, 1000);
```
## Props

### 특징
~~~
-읽기 전용(?). 즉, 변경할 수 없음
-속성이 다른 엘리먼트를 생성하려면 새로운 props를 컴포넌트에 전달하면 된다.
~~~

### props 사용법
```
function App(props){
  return(
    <Profile
    name="박소영"
    introduction="안녕하세요"
    viewCount=(1500)
    />
  );
}
```

## 컴포넌트
~~~
-리액트는 컴포넌트 기반의 구조를 갖습니다.

- 컴포넌트 구조라는 것은 작은 컴포넌트가 모여 큰컴포넌트를 구성하고,
  다시 이런 컴포넌트들이 모여서 전체페이지를 구성한다는 것을 의미합니다.

- 컴포넌트 재사용이 가능하기 때문에 전체 코드의 양을 줄일 수있어 \
  개발 시간과 유지보수 비용도 줄일 수 있습니다.

- 컴포넌트는 자바스크립트 함수와 입력과 출력이 있다는 면에서는 유사합니다.

- 다만 입려고가 출력은 입력은 props가 담당하고 출력은 리액트 엘리먼트의 형태로 출력됩니다.

- 엘리먼트를 필요한 만큼 만들어 사용한다는 면에서 객체 지향의 개념과 비슷하다.
~~~



### 1. 컴포넌트 종류
> 함수컴포넌트

> 클래스 컴포넌트
~~~
- 리액트 초기버전을 사용할 때는 클래스형 컴포넌트를 주로 사용했습니다.
  이후 Hook이라는 개념이 나오면서 최근에는 함수형 컴포넌트를 주로 사용합니다.
~~~
#### 아래의 코드는
1. App 컴포넌트에서 props를 인자로 받아
2. 내부의 Profile 컴포넌트로 전달해서 name, introduction, viewCount에 각각 속성을 할당하는,
3. 이때 전달되는 props는 다음과같은 자바스크립트 객체입니다.

```
{
  name: "박소영",
  inroduction: "안녕하세요",
  viewCount: 1500
}
```
### 2. 컴포넌트 이름짓기

> 이름은 항상 대문자로 시작
~~~
 리액트는 소문자로 시작하는 컴포넌트를 DOM태그로 인식하기 때문이다.
(컴포넌트 파일 이름과 컴포넌트 이름은 같게합니다.)
~~~
### 3.  컴포넌트 추출

~~~
복잡한 컴포넌트를 쪼개서 여러개의 컴포넌트로 나눌 수 있다.
-> 큰 컴포넌트에서 일부를 추출해서 새로운 컴포넌트를 만드는 것
 (단, 실무에서는 1개의 컴포넌트에 하나의 기능만 사용하도록 설계하는 것이 좋다.)
~~~





---
## 23.03.16 (3주차) <img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=React&logoColor=white"/>
---
###  README 작성요령 
 

1. 이름h1
2. 강의날짜 h2
3. 학습내용(필수): h2 이하 사이즈 자유사용
4. 작성코드(선택)
5. 최근날짜가 가장 위에 올라오게 하기
6. 날짜별 구분이 잘가도록 작성

---



참고교재 **<소플의 처음만난 리액트>**

---
개발환경 준비 (node.js)
###  **REACT**
 >- React = 사용자 인터페이스를 만들기 위한 자바스크립트 라이브러리
 
 ### **장점**
 >1.  빠른 업데이트와 렌더링 속도 (Virtual DOM)
 >       - DOM은 동기식, Virtual DOM은 비동기식 방법으로 렌더링
 >2. 컴포넌트 기반 구조
 >    - 리액트의 모든 페이지는 컴포넌트로 구성됩니다.
 >    - 하나의 컴포넌트는 다른 여러개의 컴포넌트의 조합으로 구성가능.
 >    - 그래서 리액트로 개발을 하다 보면 <br> 레고 블록을 조립나는 것처럼 컴포넌트를 조합해서 웹사이트를 개발.
 >    - 재사용성이 뛰어나다.
 >3. 재사용성
 >    - 반복적인 작업을 줄여주기 때문에 생간성을 높여 줍니다.
 >    - 유지보수가 용이하다
 >    - 재사용이 가능 하려면 해당 모듈의 의존성이 없어야한다.
 >4. 든든한 지원군
 >    - 메타(구 페이스북)에서 오픈소스 프로젝트로 관리하고있어 계속 발전
 >5. 활발한 지식 공유 & 커뮤니티 
 >6. 모바일 앱 개발가능
 >    - 리액트 네이티브라는 모바일 환경 UI 프레임 워크를 사용하면<br> 크로스 플랫폼(cross-platform) 모바일 앱을 개발할 수 있다.

### **단점**
>1. 방대한 학습량
>    - 자바스크립트를 공부한 경우 빠르게 학습할 수 있다.
>2. 높은 상태 관리 복잡도
>    - state, component life cycle 등의 개념이 있지만 그리 어렵지 않다.

---
### **실습 creat-react-app**

<pre>
<code>
$ npx create-react-app
</code>
</pre>
