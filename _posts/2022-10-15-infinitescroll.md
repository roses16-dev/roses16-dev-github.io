---
layout: single
title: "[react] Scroll event를 이용하여 Infinite Scroll 구현하기"
categories: react
tags: react
toc: true
sidebar:
  nav: "docs"
---

Infinite scroll을 구현하는 데에는 여러 방법이 있는데 그 중 scroll event를 이용하여 만들었다. 그 외 다른 방법은 아래 출처에 게시되어있다.



#### useInfiniteScroll.js

---

현재 유저가 보고있는 view의 위치와 document의 전체 길이를 비교해서 유저가 보고있는 view가 document의 제일 아래인지를 확인하고,

가장 아래일 때 `isFetching`은 true를 반환하며 `useEffect(() => {}, [isFetching]) ` 함수를 통해 isFetching이 true일 경우 매개변수로 전달된  callback함수를 실행하는 custom hook이다.

```javascript
import { useState, useEffect } from "react"
// scroll event가 연속적으로 발생하지 않도록 throttle을 사용하여 최적화한다. lodash package 설치가 필요하다.
import { throttle } from "lodash";

const THROTTLE_WAIT = 300;

export default function useInfiniteScroll(fetchCallback){
    const [isFetching, setIsFetching] = useState(false);

    // 유저가 보고있는 view가 document의 제일 아래인지 체크하는 함수
    // window.innerHeight : 뷰포트 높이를 px단위로 나타낸다.
    // document.documentElement.scrollTop : 스크롤의 위치를 px단위로 나타낸다. 가장 위는 0 아래로 내려갈수록 값이 커진다.
    // document.documentElement.offsetHeight : border를 포함한 박스의 길이
    const handleScrollThrottle = throttle(() => {
        if(window.innerHeight + document.documentElement.scrollTop >= document.documentElement.offsetHeight){
            setIsFetching(true);
        }
    }, THROTTLE_WAIT);
	
    // Scroll Eventlistener를 등록하여 scroll event가 발생하면 handleScrollThrottle함수를 통해 유저의 view 위치를 계산한다. 
    useEffect(() => {
        window.addEventListener('scroll', handleScrollThrottle);
        return () => {
            window.removeEventListener('scroll', handleScrollThrottle);
        }
    }, []);
    
    // isFetching값이 true가되면 매개변수로 전달받은 콜백함수를 실행한다.
    useEffect(() => {
        if(!isFetching) {
            return;
        }
        fetchCallback();
    }, [isFetching])

    return [isFetching, setIsFetching]
}
```



#### 📌 출처

> - https://ha-young.github.io/2021/frontend/infinite-scroll/
