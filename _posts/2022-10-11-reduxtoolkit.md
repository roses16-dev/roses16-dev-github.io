---
layout: single
title: "[react] Redux toolkit ( RTK )"
categories: react
tags: react redux_toolkit
toc: true
sidebar:
  nav: "docs"
---

리덕스 툴킷(RTK)은 리덕스를 더 편하게 쓰기 위해 만들어진 것이다.



#### 사용하기 

---

기존 Redux 사용 방식에서 변경된 점에 대한 정리.



- 설치하기

  ```bash
  yarn add react-redux @reduxjs/toolkit
  ```

  

- 설정코드작성

  ```javascript
  import { configureStore } from "@reduxjs/toolkit";
  import counter from "../modules/counterSlice";
  import todos from "../modules/todosSlice";
  
  const store = configureStore({
    reducer: { counter: counter, todos: todos },
  });
  
  export default store;
  ```

  rootReducer와 Store를 각각 만들어야했던 부분이 하나로 통합되었다.

  

- 모듈작성

  ```jsx
  import { createSlice } from "@reduxjs/toolkit";
  
  const initialState = {
    number:0 ,
  };
  
  const counterSlice = createSlice({
    name: "number",
    initialState,
    reducers: {
        addNumber: (state, action) => {
            state.number = state.number + action.payload
        }, 
        subNumber: (state, action) => {
            state.number = state.number - action.payload
        }, 
    },
  });
  
  export const { addNumber, subNumber } = counterSlice.actions;
  export default counterSlice.reducer;
  ```

  분리되어있던 Action 설정이 하나로 통합되었다.