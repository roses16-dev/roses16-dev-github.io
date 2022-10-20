---
layout: single
title: "[react] Redux Dev Tools Development server에서만 실행되게 설정하기"
categories: react
tags: react
toc: true
sidebar:
  nav: "docs"
---



`devTools: process.env.NODE_ENV !== 'production'`  구문을 리듀서에 추가하여 설정할 수 있다.

`process.env.NODE_ENV` : 빌드 시 'development' 또는 'production' 문자열로 대체된다.

```javascript
import { configureStore } from "@reduxjs/toolkit";

const store = configureStore({
  reducer: { },
  devTools: process.env.NODE_ENV !== 'production'
}, );

export default store;
```



#### 출처

> - 갓재명님...🤩
> - https://ui.toast.com/weekly-pick/ko_20191212