# Complete React

## React는 사용자 인터페이스를 구축하기 위한 선언적이고 효율적이며 유연한 JavaScript 라이브러리

### React가 동작하는 원리

HTML은 브라우저가 문서 객체 모델(DOM)을 구성하기 위해 따라야 하는 절차라고 말할 수 있습니다. HTML 문서를 이루는 엘리먼트는 브라우저가 HTML 문서를 읽어 들이면 DOM 엘리먼트가 되고, 이 DOM이 화면에 사용자 인터페이스를 표시합니다. 리액트는 이러한 DOM 엘리먼트를 직접 조작하지 않습니다. 대신 가상 DOM을 다루며 리액트가 가상 DOM을 생성하고 브라우저가 이를 렌더링하도록 하는 방식을 따릅니다. 이러한 가상 DOM을 리액트 엘리먼트라고 합니다. 리액트 엘리먼트는개념상 HTML 엘리먼트와 비슷하지만 실제로는 자바스크립트 객체입니다. 따라서 HTML의 DOM API를 직접 다루는 것보다 자바스크립트 객체인 리액트 엘리먼트를 직접 다루는 편이 훨씬 빠릅니다.

**※DOM(Documnet Object Model)?**

JavaScript Node 개체의 계층화된 트리로, HTML, XML 문서의 프로그래밍 API이다. 문서의 구조화된 표현을 제공하며 프로그래밍 언어가 DOM 구조에 접근할 수 있는 방법을 제공한다.

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

예제1)

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

예제2)

state는 내부에서 변경할 수 있다.

변경할 때는 언제나 setState()라는 함수를 사용한다.

```jsx
// Counter.js
import React, { Component } from 'react';

class Counter extends Component {

  state = {
    number: 0
  }

// custom 함수는 람다 함수로 작성해야 한다. 안그러면 함수 내부에서 this를 찾을 수 없다.
// 아니면 아래와 같은 생성자 작업으로 함수 내부에서 this를 사용할 수 있도록 해줘야 한다.
/*
  constructor(props) {
    super(props);
    this.handleIncrease = this.handleIncrease.bind(this);
    this.handleDecrease = this.handleDecrease.bind(this);
  }
*/

  handleIncrease = () => {
    this.setState({
      number: this.state.number + 1
    })
  }

  handleDecrease = () => {
    this.setState({
      number: this.state.number - 1
    })    
  }

  render() {
    return {
      <div>
        <h1>카운터</h1>
        <div>값: {this.state.number}</div>
        <button onClick={this.handleIncrease}>+</button>
        <button onClick={this.handleDecrease}>-</button>
      </div>
    }
  }
}

export default Counter;
```

```jsx
// App.js
import React, { Component } from 'react';
import MyName from './MyName';

class App extends Component {
  render() {
    return <Counter />;
  }
}

export default App;
```

## 생명주기 메서드를 클래스에 추가하기

많은 컴포넌트가 있는 애플리케이션에서 컴포넌트가 삭제될 때 해당 컴포넌트가 사용 중이던 리소스를 확보하는 것이 중요합니다. Clock이 처음 DOM에 렌더링 될 때마다 타이머를 설정하려고 합니다. 이것은 React에서 “마운팅”이라고 합니다. 또한 Clock에 의해 생성된 DOM이 삭제될 때마다 타이머를 해제하려고 합니다.

컴포넌트 클래스에서 특별한 메서드를 선언하여 컴포넌트가 마운트되거나 언마운트 될 때 일부 코드를 작동할 수 있습니다.

```jsx
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

//컴포넌트 마운트
  componentDidMount() {
  }

//컴포넌트 언마운트
  componentWillUnmount() {
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

이러한 메서드들은 “생명주기 메서드”라고 불립니다.

componentDidMount() 메서드는 컴포넌트 출력물이 DOM에 렌더링 된 후에 실행됩니다. 이 장소가 타이머를 설정하기에 좋은 장소입니다.

```jsx
componentDidMount() {
    this.timerID = setInterval(
      () => this.tick(),
      1000
    );
  }
```

`this` (`this.timerID`)에서 어떻게 타이머 ID를 제대로 저장하는지 주의해주세요.

`this.props`가 React에 의해 스스로 설정되고 `this.state`가 특수한 의미가 있지만, 타이머 ID와 같이 데이터 흐름 안에 포함되지 않는 어떤 항목을 보관할 필요가 있다면 자유롭게 클래스에 수동으로 부가적인 필드를 추가해도 됩니다.

`componentWillUnmount()` 생명주기 메서드 안에 있는 타이머를 분해해 보겠습니다.

```jsx
componentWillUnmount() {
    clearInterval(this.timerID);
  }
```

마지막으로 `Clock` 컴포넌트가 매초 작동하도록 하는 `tick()`이라는 메서드를 구현해 보겠습니다.

이것은 컴포넌트 로컬 state를 업데이트하기 위해 `this.setState()`를 사용합니다.

```jsx
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  componentDidMount() {
    this.timerID = setInterval(
      () => this.tick(),
      1000
    );
  }

  componentWillUnmount() {
    clearInterval(this.timerID);
  }

  tick() {
    this.setState({
      date: new Date()
    });
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

이제 시계는 매초 째깍거립니다.

현재 어떤 상황이고 메서드가 어떻게 호출되는지 순서대로 빠르게 요약해 보겠습니다.

1. `<Clock />`가 `ReactDOM.render()`로 전달되었을 때 React는 `Clock` 컴포넌트의 constructor를 호출합니다. `Clock`이 현재 시각을 표시해야 하기 때문에 현재 시각이 포함된 객체로 `this.state`를 초기화합니다. 나중에 이 state를 업데이트할 것입니다.
2. React는 `Clock` 컴포넌트의 `render()` 메서드를 호출합니다. 이를 통해 React는 화면에 표시되어야 할 내용을 알게 됩니다. 그 다음 React는 `Clock`의 렌더링 출력값을 일치시키기 위해 DOM을 업데이트합니다.
3. `Clock` 출력값이 DOM에 삽입되면, React는 `componentDidMount()` 생명주기 메서드를 호출합니다. 그 안에서 `Clock` 컴포넌트는 매초 컴포넌트의 `tick()` 메서드를 호출하기 위한 타이머를 설정하도록 브라우저에 요청합니다.
4. 매초 브라우저가 `tick()` 메서드를 호출합니다. 그 안에서 `Clock` 컴포넌트는 `setState()`에 현재 시각을 포함하는 객체를 호출하면서 UI 업데이트를 진행합니다. `setState()` 호출 덕분에 React는 state가 변경된 것을 인지하고 화면에 표시될 내용을 알아내기 위해 `render()` 메서드를 다시 호출합니다. 이 때 `render()` 메서드 안의 `this.state.date`가 달라지고 렌더링 출력값은 업데이트된 시각을 포함합니다. React는 이에 따라 DOM을 업데이트합니다.
5. `Clock` 컴포넌트가 DOM으로부터 한 번이라도 삭제된 적이 있다면 React는 타이머를 멈추기 위해 `componentWillUnmount()` 생명주기 메서드를 호출합니다.

lifecycle api

![Untitled](https://user-images.githubusercontent.com/45458274/126184626-952c2fa9-f0e6-4c02-b8ab-71560a47d984.png)

- constructor
    - 컴포넌트가 처음 브라우저에 나타날 때
    - State 초기 설정, 미리 해야하는 작업들
- getDerivedStateFromProps
    - props로 받은 값을 state에 그대로 동기화를 시키고 싶은 경우
    - Mounting 단계, Updating 단계 모두 실행된다.
- render
    - 어떤 DOM을 만들고 어떤 값을 정의할지 정의한다.
- componentDidMount
    - 외부 라이브러리를 사용할 때 특정 DOM에 어떤 처리를 한다던지, ajax 요청 등을 할 때 사용한다.
    - 컴포넌트가 나타난 다음에 어떤 작업을 할지를 명시한다. 이벤트 리스닝, API 요청 등
- **shouldComponentUpdate**
    - 컴포넌트가 업데이트되는 성능을 최적화시키고 싶을 때 사용한다.
    - 바뀌지 않은 컴포넌트에 대해서는 render 함수를 타지 않도록 한다. (true, false 반환)
- getSnapshotBeforeUpdate
    - 렌더링이 끝난 후 브라우저에 반영되기 직전에 호출되는 함수
- componentDidUpdate
    - 컴포넌트 업데이트 후 호출되는 함수
- componentWillUnmount
    - componentDidMount에서 설정한 리스너를 해제하는 역할