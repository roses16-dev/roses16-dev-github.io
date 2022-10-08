---
layout: single
title: "[react] React Router dom"
categories: react
tags: react react_router_dom
toc: true
sidebar:
  nav: "docs"
---

React Router dom은 SPA 방식 사이트에 페이지 이동을 구현해주는 패키지이다.

> 공식문서  https://reactrouter.com/en/v6.3.0



#### 준비하기

---

- 설치하기

  ```bash
  yarn add react-router-dom
  ```



#### Router 생성 및 적용하기

---

1. **page component 생성**

   여러개의 페이지를 컴포넌트 형식으로 만든다.

   

2. **Router.js 생성 및 route 설정 코드 작성**

   Router의 기능처럼 URL(Route)과 페이지 컴포넌트를 매칭시킨다.

   ```jsx
   // src/chared/Router.js
   
   import React from "react";
   // React Router dom을 사용하기 위한 package import
   import { BrowserRouter, Route, Routes } from "react-router-dom";
   
   // 제작한 pages import
   import Home from "../pages/Home";
   
   // Router 설정
   const Router = () => {
     return (
       <BrowserRouter>
         <Routes>
           <Route path="/" element={<Home />} />
         </Routes>
       </BrowserRouter>
     );
   };
   
   export default Router;
   ```

   

3. **최상위 컴포넌트 `App.js`에 `Router.js`를 Import 한 후 Router 컴포넌트를 return 한다.**

   ```jsx
   import Router from './shared/Router';
   function App() {
     return <>
            	<Router />
            </>
   }
   ```





#### Dynamic Route 사용하기

---

동적 라우팅. path에 유동적인 값을 가지고 이동할 수 있게 한다.

- **Route 설정**

  기존에 작성한  `Router.js` 내용과 동일하다. 그 중 유동적인 값과 함께 이동할 페이지에 아래와 변수명을 추가한다. 

  ```jsx
  // src/chared/Router.js
  // ...
  const Router = () => {
    return (
      <BrowserRouter>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/detail/:id" element={<Detail />} /> {* ◀ *}
        </Routes>
      </BrowserRouter>
    );
  };
  // ...
  ```

  path `:id` 부분에 어떤 값이 입력되어도 `<Detail/>` 컴포넌트로 이동한다.



- `:id` 읽어오기

  `useParams()`를 이용하여 이동한 컴포넌트에서 `:id`값을 읽어와 해당하는 데이터를 보여주게 한다.

  ```jsx
  import { useParams } from "react-router-dom"
  
  export default const Detail = () => {
      console.log(useParams())			// console 출력 : { id: '123'} 
  }
  ```

  

#### Hooks

---

일부 Hook이며 더 많은 내용은 공식문서 참조

- `useNavigate()`

  다른 페이지로 이동시켜 준다.

  컴포넌트 내에서 `const navigate = useNavigate()` Navigate 함수를 반환받고 `navigate("경로");` 로 이동한다.

  

- `useLocation()`

  현재 페이지의 pathname, key 등여러가지 정보를 얻을 수 있다.

  

- `Link`

  Hook이 아닌 API이다. HTML의 `a`태그 기능을 한다.

  