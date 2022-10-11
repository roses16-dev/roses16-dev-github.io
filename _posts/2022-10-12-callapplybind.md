---
layout: single
title: "[javascript] call, apply, bind"
categories: javascript
tags: javascript
toc: true
sidebar:
  nav: "docs"
---

call, apply, bind에 대한 정리 📚



#### call

 모든 함수에서 사용할 수 있으며 this를 특정값으로 지정할 수 있다.

첫번째 매개변수로 `this`로 사용할 값을 입력하면 해당 함수의 this는 입력한 값으로 대체된다. this를 사용할 필요가 없다면 `null`을 입력하여 사용할 수 있다.

```javascript
const obj = { name: 'Jane'}

function f (age, gender) {
    this.age = age
    this.gender = gender
    console.log(this)
}

f.call(obj, 10, female)			// { name: Jane, age: 10, gender: female }
```



#### apply

call과 같은 역할을 한다. 단, 매개변수를 배열로 받는다.

```javascript
const obj = { name: 'Jane'}

function f (age, gender) {
    this.age = age
    this.gender = gender
    console.log(this)
}

f.apply(obj, [10, female])			// { name: Jane, age: 10, gender: female }
```



#### bind

call, apply와 같은 역할이나 this 값을 영구히 바꿀 수 있다.

```javascript
const obj = { name: 'Jane'}

function f () {
    console.log(this.name)
}
f()							// undefined

const f_bind = f.bind(obj)
f_bind()					// Jane
```



#### 출처

> - https://www.youtube.com/watch?v=KfuyXQLFNW4&list=PLZKTXPmaJk8JZ2NAC538UzhY_UNqMdZB4&index=13