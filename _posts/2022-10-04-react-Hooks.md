---
layout: single
title: "[react] Hooks가 만들어진 이유"
categories: react hooks
tags: 수정필요
toc: true
sidebar:
  nav: "docs"
---



#### 1. 컴포넌트 라이프 사이클에 따른 관리를 용이하게 하기 위해

리액트에서는 컴포넌트를 class와 function으로 만들 수 있다. 

- Class 컴포넌트

  ```jsx
  class App extends Component{
      constructor(props){
          
      }
  
      componenetDidMount(){
          
      }
      
      render(){
          return <div></div>
      }
  }
  ```

  

- Function 컴포넌트

  ```jsx
  function App() {
      return <div></div>
  }
  ```

  

두 형태의 가장 큰 차이는 내장 메소드에 있다. 

Class 컴포넌트는 `constructor()`, `componenetDidMount()` 등과 같이 컴포넌트의 라이프 주기 (생성-업데이트-소멸) 에 호출되는 함수를 미리 정의할 수 있지만 Function 컴포넌트는 이 점이 불가능하다. 

Hooks는 이를 보완하고, 보다 간편하게 사용하기 위해 만들어졌다.



#### 2. HOC 컴포넌트 사용 시 발생하는 Wrapper 컴포넌트의 과잉을 줄여준다.

HOC 컴포넌트는 Hooks가 만들어지기 추천되었던 방식이다.

**재사용이 가능한 로직만을 분리하여 Component로 만드는데 이를 HOC component라고 하며** 반복되지 않는 요소들은 parameter로 받아 처리한다. 

단 이 방식은 Wrapper 컴포넌트가 과하게 발생할 수 있고, 이 때문에 데이터 흐름을 파악하기 어려워 진다는 단점이 있었다.

Hooks의 Custom React Hooks는 이러한 방식을 대체하여 Wrapper 컴포넌트를 줄일 수 있다.





#### 참조

> - https://www.youtube.com/watch?v=C26vJqelKlA&t=26s