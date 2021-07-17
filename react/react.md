# Complete React

## React는 사용자 인터페이스를 구축하기 위한 선언적이고 효율적이며 유연한 JavaScript 라이브러리

### React가 동작하는 원리

HTML은 브라우저가 문서 객체 모델(DOM)을 구성하기 위해 따라야 하는 절차라고 말할 수 있습니다. HTML 문서를 이루는 엘리먼트는 브라우저가 HTML 문서를 읽어 들이면 DOM 엘리먼트가 되고, 이 DOM이 화면에 사용자 인터페이스를 표시합니다. 리액트는 이러한 DOM 엘리먼트를 직접 조작하지 않습니다. 대신 가상 DOM을 다루며 리액트가 가상 DOM을 생성하고 브라우저가 이를 렌더링하도록 하는 방식을 따릅니다. 이러한 가상 DOM을 리액트 엘리먼트라고 합니다. 리액트 엘리먼트는개념상 HTML 엘리먼트와 비슷하지만 실제로는 자바스크립트 객체입니다. 따라서 HTML의 DOM API를 직접 다루는 것보다 자바스크립트 객체인 리액트 엘리먼트를 직접 다루는 편이 훨씬 빠릅니다.

**※DOM(Documnet Object Model)?**

: JavaScript Node 개체의 계층화된 트리로, HTML, XML 문서의 프로그래밍 API이다. 문서의 구조화된 표현을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공한다.

### React의 특징

-**컴포넌트 기반의 라이브러리**

헤더, 메인 콘텐츠, 버튼, 사이드바 메뉴 같은 것들을 헤더 컴포넌트, 사이드바 컴포넌트와 같이 하나의 컴포넌트로 묶어서 관리할 수 있다. 따라서 리액트를 개발하다가 특정 부분에서 오류가 생기면 그 컴포넌트만 수정하여 사용할 수 있다. 코드의 재사용성과 유지보수성을 증가시켜 준다.

-**단방향 데이터 바인딩(One Way Data Flow)**

리액트는 데이터의 흐름이 한 방향으로만 흐른다. 데이터가 내려가기만 하고 밑에서 데이터를 올려줄 수 없기떄문에 부모의 데이터를 바꾸기 위해서는 state를 이용해야 한다.

-**Props and State**

Props: 부모 컴포넌트에서 자식 컴포넌트로 전달해주는 데이터이다. 자식 컴포넌트에서 전달 받은 props는 변경이 불가능하고 props를 전달해준 최상위 부모 컴포넌트만 props를 변경할 수 있다.

State: 사용자와의 상호작용을 통해 데이터를 동적으로 변경해야 하는 것과 같이 동적인 데이터를 다룰 때 사용한다. 각각의 state는 독립적이라 다른 컴포넌트에 직접적인 접근은 불가능하다. 그러나 자신보다 상위에 있는 state는 변경이 가능하지만 state를 변경해주는 함수를 props로 받는다면 state의 변경이 가능하다.

-**Virtual DOM**

가상의 Document Object Mode.로 실제 DOM을 조작하는게 아닌, DOM을 추상화 한 자바스크립트 객체를 구상해 사용한다.

### React의 장단점

**장점**

- 배우기가 간단하고, 애플리케이션을 만들 때 복잡함이 적다.
- Controller, directive, template, model 처럼 분리를 하지 않고 Component 단 하나로 관리한다.
- 뛰어난 Garbage Collection, 메모리 관리, 성능을 가지고 있다.
- 서버 사이드 렌더링과 클라이언트 렌더링을 둘 다 지원한다.
- 간편한 UI 수정과 재사용이 용이하다.
- 다른 프레임워크나 라이브러리와 혼용하여 사용할 수 있다. 즉, 개발이 완료된 서비스에도 적응이 가능하다.

**단점**

- 보여지는 부분에만 관여하기때문에 데이터 모델링, Routing, Ajax 등등의 기능을 제공하지 않는다.
- view 외 기능들은 직접 구현하거나 라이브러리를 사용하여 구현해야 하기 때문에 JavaScript 배경지식이 부족할 경우애는 사용이 힘들다.
- IE8 이하 버전들을 지원하지 않는다.

# React 실습

### Webpack과 Babel

**Webpack**

서로 의존하는 여러 확장자의 파일들을 bundling 하여 미리 정한 규칙을 통해 단일 static파일들로 만드는 도구이다.

**Babel**

자바스크립트 변환 도구이다. ES6같은 최신 모던 JavaScript문법을 구 브라우저에서 작동될 수 있도록 해준다.

## React 기본 구조

class 형태의 컴포넌트

```jsx
import React, { Component } from 'react';

class App extends Component {
	render(){
			return(
				<div>
					<h1>Hello World</h1>
				</div>
			);
	}
}
```

Function 형태의 컴포넌트

```jsx
const App = () => {
		return(
		<div>
				<h1>Hello World</h1>
		</div>
		);
}
```

DOM에 엘리먼트 렌더링 하기

```jsx
const element = <h1>Hello, world</h1>;
ReactDOM.render(element, document.getElementById('root'));
```

렌더링 된 엘리먼트 업데이트하기

```jsx
function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  ReactDOM.render(element, document.getElementById('root'));
}

setInterval(tick, 1000);
```

## Component와 Props

React 엘리먼트는 사용자 정의 컴포넌트로도 나타낼 수 있습니다.

```jsx
const element = <Welcome name="Sara" />;
```

React가 사용자 정의 컴포넌트로 작성한 엘리먼트를 발견하면 JSX 어트리뷰트와 자식을 해당 컴포넌트에 단일 객체로 전달합니다. 이 객체를 “props”라고 합니다.

다음은 페이지에 “Hello, Sara”를 렌더링하는 예시입니다.

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

const element = <Welcome name="Sara" />;
ReactDOM.render(
  element,
  document.getElementById('root')
);
```

이 예시에서는 다음과 같은 일들이 일어납니다.

1. `<Welcome name="Sara" />` 엘리먼트로 `ReactDOM.render()`를 호출합니다.
2. React는 `{name: 'Sara'}`를 props로 하여 `Welcome` 컴포넌트를 호출합니다.
3. `Welcome` 컴포넌트는 결과적으로 `<h1>Hello, Sara</h1>` 엘리먼트를 반환합니다.
4. React DOM은 `<h1>Hello, Sara</h1>` 엘리먼트와 일치하도록 DOM을 효율적으로 업데이트합니다.

### Component 합성

컴포넌트는 자신의 출력에 다른 컴포넌트를 참조할 수 있습니다. 이는 모든 세부 단계에서 동일한 추상 컴포넌트를 사용할 수 있음을 의미합니다. React 앱에서는 버튼, 폼, 다이얼로그, 화면 등의 모든 것들이 흔히 컴포넌트로 표현됩니다.

예를 들어 Welcome을 여러 번 렌더링하는 App 컴포넌트를 만들 수 있습니다.

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return (
    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  );
}

ReactDOM.render(
  <App />,
  document.getElementById('root')
);
```

일반적으로 새 React 앱은 최상위에 단일 App 컴포넌트를 가지고 있습니다. 하지만 기존 앱에 React를 통합하는 경우에는 Button과 같은 작은 컴포넌트부터 시작해서 뷰 계층의 상단으로 올라가면서 점진적으로 작업해야 할 수 있습니다.

### Component 추출

다음 Comment 컴포넌트를 살펴봅시다.

```jsx
function Comment(props) {
  return (
    <div className="Comment">
      <div className="UserInfo">
        <img className="Avatar"
          src={props.author.avatarUrl}
          alt={props.author.name}
        />
        <div className="UserInfo-name">
          {props.author.name}
        </div>
      </div>
      <div className="Comment-text">
        {props.text}
      </div>
      <div className="Comment-date">
        {formatDate(props.date)}
      </div>
    </div>
  );
}
```

이 컴포넌트는 `author`(객체), `text`(문자열) 및 `date`(날짜)를 props로 받은 후 소셜 미디어 웹 사이트의 코멘트를 나타냅니다.

이 컴포넌트는 구성요소들이 모두 중첩 구조로 이루어져 있어서 변경하기 어려울 수 있으며, 각 구성요소를 개별적으로 재사용하기도 힘듭니다. 이 컴포넌트에서 몇 가지 컴포넌트를 추출하겠습니다.

먼저 Avatar를 추출하겠습니다.

```jsx
function Avatar(props) {
  return (
    <img className="Avatar"
      src={props.user.avatarUrl}
      alt={props.user.name}
    />
  );
}
```

`vatar` 는 자신이 `Comment` 내에서 렌더링 된다는 것을 알 필요가 없습니다. 따라서 props의 이름을 `author`에서 더욱 일반화된 `user`로 변경하였습니다.

props의 이름은 사용될 context가 아닌 컴포넌트 자체의 관점에서 짓는 것을 권장합니다.

이제 Comment 가 살짝 단순해졌습니다.

```jsx
function Comment(props) {
  return (
    <div className="Comment">
      <div className="UserInfo">
        <Avatar user={props.author} />
        <div className="UserInfo-name">
          {props.author.name}
        </div>
      </div>
      <div className="Comment-text">
        {props.text}
      </div>
      <div className="Comment-date">
        {formatDate(props.date)}
      </div>
    </div>
  );
}
```

다음으로 Avatar 옆에 사용자의 이름을 렌더링하는 UserInfo 컴포넌트를 추출하겠습니다.

```jsx
function UserInfo(props) {
  return (
    <div className="UserInfo">
      <Avatar user={props.user} />
      <div className="UserInfo-name">
        {props.user.name}
      </div>
    </div>
  );
}
```

처음과 비교할때 Comment가 단순해졌습니다.

```jsx
function Comment(props) {
  return (
    <div className="Comment">
      <UserInfo user={props.author} />
      <div className="Comment-text">
        {props.text}
      </div>
      <div className="Comment-date">
        {formatDate(props.date)}
      </div>
    </div>
  );
```

처음에는 컴포넌트를 추출하는 작업이 지루해 보일 수 있습니다. 하지만 재사용 가능한 컴포넌트를 만들어 놓는 것은 더 큰 앱에서 작업할 때 두각을 나타냅니다. UI 일부가 여러 번 사용되거나 (Button, Panel, Avatar), UI 일부가 자체적으로 복잡한 (App, FeedStory, Comment) 경우에는 별도의 컴포넌트로 만드는 게 좋습니다.

## Props는 읽기 전용입니다.

함수 컴포넌트나 클래스 컴포넌트 모두 컴포넌트의 자체 props를 수정해서는 안 됩니다. 다음 sum 함수를 살펴봅시다.

```jsx
function sum(a, b) {
  return a + b;
}
```

이런 함수들은 [순수 함수](https://en.wikipedia.org/wiki/Pure_function)라고 호칭합니다. 입력값을 바꾸려 하지 않고 항상 동일한 입력값에 대해 동일한 결과를 반환하기 때문입니다.

반면에 다음 함수는 자신의 입력값을 변경하기 때문에 순수 함수가 아닙니다.

```jsx
function withdraw(account, amount) {
  account.total -= amount;
}
```

React는 매우 유연하지만 한 가지 엄격한 규칙이 있습니다.

**모든 React 컴포넌트는 자신의 props를 다룰 때 반드시 순수 함수처럼 동작해야 합니다.**

## State and Lifecycle

이 섹션에서는 Clock 컴포넌트를 완전히 재사용하고 캡슐화하는 방법을 배울 것입니다. 이 컴포넌트는 스스로 타이머를 설정할 것이고 매초 스스로 업데이트할 것입니다.

```jsx
function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  ReactDOM.render(
    element,
    document.getElementById('root')
  );
}

setInterval(tick, 1000);
```

시계가 생긴 것에 따라 캡슐화하는 것으로 시작할 수 있습니다.

```jsx
function Clock(props) {
  return (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {props.date.toLocaleTimeString()}.</h2>
    </div>
  );
}

function tick() {
  ReactDOM.render(
    <Clock date={new Date()} />,
    document.getElementById('root')
  );
}

setInterval(tick, 1000);
```

그러나 여기에는 중요한 요건이 누락되어 있습니다. Clock이 타이머를 설정하고 매초 UI를 업데이트하는 것이 Clock의 구현 세부사항이 되어야 합니다.

이상적으로 한 번만 코드를 작성하고 Clock이 스스로 업데이트하도록 만들려고 합니다.

```jsx
ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```

이것을 구현하기 위해서 Clock 컴포넌트에 “state”를 추가해야 합니다.

State는 props와 유사하지만, 비공개이며 컴포넌트에 의해 완전히 제어됩니다.

🛠️  함수에서 클래스로 변환하는 방법

1. `React.Component`를 확장하는 동일한 이름의 [ES6 class](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Classes)를 생성합니다.
2. `render()`라고 불리는 빈 메서드를 추가합니다.
3. 함수의 내용을 `render()` 메서드 안으로 옮깁니다.
4. `render()` 내용 안에 있는 `props`를 `this.props`로 변경합니다.
5. 남아있는 빈 함수 선언을 삭제합니다.

### **클래스에 로컬 State 추가하기**

1. render() 메서드 안에 있는 this.props.date를 this.state.date로 변경합니다.

```jsx
class Clock extends React.Component {
  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}
```

1. 초기 this.state를 지정하는 class constructor를 추가합니다.

```jsx
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}
```

여기서 어떻게 props를 기본 constructor에 전달하는지 유의하십시오.

```jsx
constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }
```

클래스 컴포넌트는 항상 props로 기본 constructor를 호출해야 합니다.

1. <Clock /> 요소에서 date prop을 삭제합니다.

```jsx
ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```

결과는 다음과 같습니다.

```jsx
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}

ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```