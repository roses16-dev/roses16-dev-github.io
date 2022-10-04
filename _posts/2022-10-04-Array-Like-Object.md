---
layout: single
title: "[javascript] 유사배열 (Array-like Object)"
categories: javascript
toc: true
sidebar:
  nav: "docs"

---



유사 배열은 배열과 비슷한 형태의 객체(Object)를 말한다.

객체의 Key값에 숫자형태의 indexing을 사용하여 배열과 유사한 형태를 갖는다.

```jsx
let arrLikeObj = { 0:'A', 1:'B', 2:'C' ...}
```



유사배열은 배열 객체의 method는 지원하지 않으나 length 프로퍼티는 지원한다. 

단순 배열 뿐 아니라 배열과 이를 제어하는 method를 함께 구성해야 할 때 사용된다. 배열의 method는 `Array.prototype.` 에 추가되어야 하며 다른 배열에서도 해당 메소드에 접근이 가능하지만 객체로 만들 경우 독립적인 method를 추가할 수 있다.

