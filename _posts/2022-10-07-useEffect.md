---
layout: single
title: "[react] useEffect"
categories: react
toc: true
sidebar:
  nav: "docs"

---

useEffect는 component의 life cycle에 따라 실행될 함수를 정의하는 Hook 입니다. 



#### Component life cycle

---

![image-20221007183914791](C:\Users\Minjoo\Desktop\devlog\roses16-dev.github.io\images\2022-10-07-useEffect\image-20221007183914791.png)

- Mount : Component가 브라우저에 나타나는 것
- Update : props, state 등이 바뀌는 것
- Unmount : component가 브라우저에서 사라지는 것





#### 사용하기

---

- Import

  ```jsx
  import React, {useEffect} from 'react';
  ```

  

- 함수 작성하기 : Rendering 시 실행되는 useEffect

  - Dependency array 없이 선언 : mount와 update 렌더링 마다 실행된다.

    ```jsx
    function APP() {
        useEffect( () => {
            // 실행할 코드
        })
    }
    ```

  - Dependency array와 함께 선언 : mount 렌더링 시와 dependency array 값의 update 렌더링 시에만 실행된다.

    ```jsx
    function APP() {
        useEffect( () => {
    		// 실행할 코드
        }, [dependencyArray])	// dependencyArray로 빈 배열[]을 전달할 경우 mounting 렌더링 시에만 실행된다.
    }
    ```

    ※ 꼭 배열이 아닌 다른 자료형도 들어간다 ( ! ) `[number]`

    

- 함수 작성하기 : Unmount 될 때 실행되는 useEffect ( Clean UP 함수 )

  주로 설정한 Timer나 EventListener, 라이브 인스턴스를 정리해줄 때 사용한다.

  ```jsx
  function APP() {
  	useEffect( () => {
          
          return (
              // 실행할 코드
          )
      })
  }
  ```

  ※ dependencyArray가 설정되어있다면, unmount 시와 dependencyArray의 값이 변경되기 직전에도 호출된다.

※ useEffect 내에 state나 props가 사용된다면 dependencyArray에 해당 값을 넣어주어야 state와 props의 변경 시 변경된 값을 사용할 수 있따.





출처 

> - https://www.youtube.com/watch?v=kyodvzc5GHU&t=12s