---
layout: single
title: "[javascript] Optional Chaining"
categories: javascript
tags: javascript
toc: false
sidebar:
  nav: "docs"
---

 Optional Chaining에 대한 정리 📕



`?.` 으로 표현하며 프로퍼티가 없는 중첩 객체에 접근했을 때 Undefined를 반환하여 안전하게 접근할 수 있게 한다.

```javascript
const obj = { name: { first: 'A', last: 'B' }}

obj.address			 // undefined
obj.address.middle	 // TypeError
obj.address?.middle  // undefined
```

프로퍼티의 존재 여부가 불확실한 데이터에 접근할 때 사용한다.

※ 꼭 필요할때만 사용하고, 기본적으로는 예외처리를 꼼꼼히 해야한다.
