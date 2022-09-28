---
layout: single
title: "[javascript] 언더바(_)로 변수명을 선언하는 이유"
categories: javascript
tags: javascript, ETC

toc: true
---


언더바(_) 변수명은 주로 함수 선언 시 매개변수명으로 사용되는 편인데, 이는 해당 매개변수가 중요하지않다는 것을 표현하기 위한 개발자들의 관습이다.

```javascript
array.map((_, i) => { /* 함수부분 */})
```

위 예시와 같이 map 함수의 매개변수는 순서대로 element와 index인데 element는 생략이 불가능한 매개변수이므로 사용하지 않더라도 변수명을 지정하여 값을 받아와야한다. 이 때 변수명을 언더바(_)로 설정하여 실제 함수에서는 사용하지 않음을 표현한다.