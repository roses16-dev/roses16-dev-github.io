---
layout: single
title: "[javascript] 논리 연산자(logical operator) or와 and의 특이점"
categories: javascript
tags: javascript basic
sidebar:
  nav: "docs"
---

### javascript  내 OR와 AND 연산자의 특이점

논리연산자는 많은 프로그래밍 언어에서 단순히 true와 false만을 반환하는 것으로 알려져 있으나 javascript 의 논리 연산자 중 or와 and는 조금 다르게 작동한다



- OR

  or 연산자는 → 방향으로 연산을 진행하며 true인 value가 나오면 해당 연산자를 반환하고 연산을 종료한다.
  때문에 비교값 중 가장 먼저 나오는 true 값을 반환하며, 값이 모두 true일 경우 가장 앞에 위치한 피연산자를, 값이 모두 false일 경우 가장 뒤에 위치한 피연산자를 반환한다. 

  ```javascript
  null || 7	// 7 → true 조건의 값을 반환
  4 || 7		// 4 → 피연산자 모두 true일 경우 가장 앞쪽의 피연산자를 반환한다.
  null || undefined	// undefined → 피연산자 모두 false일 경우 가장 뒤쪽의 피연산자를 반환한다.
  ```

  ※ null, undefined, NaN는 Boolean으로 형 변환 시 false 값으로 판단되며 이러한 값을들 falsy한 값이라고 부른다.
  ※ Infinity는 Boolean으로 형 변환 시 true 값으로 판단된다.

  

- AND
  and 연산자도 → 방향으로 연산을 진행하며 false인 value가 나오면 해당 연산자를 반환하고 연산을 종료한다.
  때문에 비교값 중 가장 먼저 나오는 false 값을 반환하며 값이 모두 true일 경우 가장 뒤에 위치한 피연산자를, 값이 모두 false일 경우 가장 앞에 위치한 피연산자를 반환한다.

  ```javascript
  7 && null	// null → false 조건의 값을 반환
  4 && 7		// 7 → 피연산자 모두 true일 경우 가장 뒤쪽의 피연산자를 반환한다.
  null && undefined	// null → 피연산자 모두 false일 경우 가장 앞쪽의 피연산자를 반환한다.
  ```

  

두 연산자 모두 반환값을 찾으면 연산이 중도에 종료되기 때문에 아래와 같은 상황이 발생할 수 있다.

```javascript
let arr = []
true || arr.push('Rolling')
console.log(arr)		// [] → true 값을 찾은 후 or 연산이 종료되어 arr.push() 함수가 실행되지 않았다.
```



이를 이용하여 falsy한 값이 문제가 될 가능성이 있을 때의 예외처리를 할 수 있다.

```javascript
let str = ""
(str.match(/\d/g)|| []).length
```

정규표현식 조건에 맞는 값이 없을 경우 `match()` 함수는 null을 반환시키며, `null.length` 명령어는 Uncaught TypeError로 동작을 멈춘다.
`|| []`를 추가하여 match 함수의 반환값이 null일 경우 빈 array를 반환하게 하여 `[].length` 라는 정상적인 명령어를 사용하게 한다.



### 참조

> - https://mynameisdabin.tistory.com/10