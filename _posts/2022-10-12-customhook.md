---
layout: single
title: "[react] Custom hook"
categories: react
tags: react
toc: true
sidebar:
  nav: "docs"
---

React의 내장 hook을 사용해서 공통된 로직이나 기능을 hook으로 생성할 수 있다. 📚



#### 사용하기

---

- 폴더 구조 만들기

  일반적으로 `scr/hooks` 폴더를 생성하여 작업한다.

  

- 필요로하는 로직을 코드로 구현한다.

  하고자 하는 기능에 따라 코드가 매우 다르며 아래는 useState와 onChage 이벤트를 통해 Input을 저장하는 방식을 cumstom hook으로 만든 것이다.

  custom hook의 이름은 use로 시작해야한다. ( 일종의 룰인것 같다.)

  ```javascript
  // src/hooks/useInput.js
  
  import React, { useState } from "react";
  
  const useInput = () => {
    const [value, setValue] = useState("");
  
    const handler = (e) => {
      setValue(e.target.value);
    };
  
    return [value, handler];
  };
  
  export default useInput;
  ```

  

- 사용하기

  마찬가지로 기대하는 기능에 따라 사용방법 또한 달라진다. 아래 예시는 위 custom hook의 사용예시이다.

  ```javascript
  import React from "react";
  import useInput from "./hooks/useInput";
  
  const COMPONENT_NAME = () => {
    const [title, onChangeTitleHandler] = useInput();
    const [body, onChangeBodyHandler] = useInput();
  
    return (
      <div>
        <input value={title} onChange={onChangeTitleHandler} />
        <input value={body} onChange={onChangeBodyHandler} />
      </div>
    );
  };
  
  export default COMPONENT_NAME;
  ```

  
