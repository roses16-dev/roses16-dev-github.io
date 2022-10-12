---
layout: single
title: "[javascript] Async, Await"
categories: javascript
tags: javascript
toc: false
sidebar:
  nav: "docs"
---

 Async와 Await는 Promise 코드를 좀 더 단순하게 작성하는 것을 도와주는 API이다. 📕

기존에 있던 것에 추가하여 사용을 간편하게 해주는 것을 syntactic sugar라고 한다.



- **Async**

  함수를 Promise 객체를 반환한다.

  ```javascript
  async function getNumber(){
      return 1;
  }					// Promise {<fulfilled>: 1}
  ```

  ```javascript
  async function getNumber(){
      throw new Error('error');
  }					// Promise {<rejected>:Error: error}
  ```

  

- **Await**

  async  내부에서 Promise 객체 앞에 사용되어 promise가 `setteled`상태가 될때까지 기다린다.

  ```javascript
  function delay(time){
    return new Promise (resolve => setTimeout(resolve, time))
  }
  
  async function getRed(){
     delay(1000);
    return '🧡';
  }
  
  async function getYellow(){
     delay(1000);
    return '💛';
  }
  
  
  async function getColors(){
    const red= await getRed();			// ← await 사용
    const yellow = await getYellow();		// ← await 사용
  
    return `${red} + ${yellow}`
  }
  console.log('시작')
  getColors().then(console.log)
  console.log('종료')
  ```
  
  ```
  시작
  종료
  🧡 + 💛		// await를 사용하지 않을 경우 [object Promise] + [object Promise] 로 출력된다.
  ```
  
  

#### 출처 

> - https://www.youtube.com/watch?v=Uh8u20MD978&list=PLZKTXPmaJk8JZ2NAC538UzhY_UNqMdZB4&index=17&t=27s
> - https://www.youtube.com/watch?v=aoQSOZfz3vQ