---
layout: single
title: "[javascript] ES와 ES5, ES6의 차이점"
categories: javascript
tags: javascript
toc: true
sidebar:
  nav: "docs"


---

#### ES( ECMA Script )란?

**'Javascript' 의 표준 규격을 의미한다. **
ECMA( European Computer Manufactures Association )는 스위스 제네바에 본부를 두고 있는 "유럽 컴퓨터 제조업자 협회"이다. 이 ECMA에서 정한 규격을 ES( ECMA Script ) 라 이야기하며, 해당 규격이 ISO에 제안/사용되는 경우가 많다.

ECMA는 여러 언어의 표준안도 결정하기때문에 여러 언어들의 표준을 구분하기 위해 숫자를 붙여 표현한다. 우리가 아는 ES5, ES6은 각각 ECMA Script 5, ECMA Script 6 의 규격을 따른다는 의미이다.

#### ES5 (2009)

- 배열에 'forEach, map, filter, reduce, some, every'와 같은 메소드들을 지원한다.
- Object에 대한 getter와 setter를 지원한다.
- strict mode를 지원한다.
- json 형식의 자료들을 지원한다.

#### ES6 (2015)

- Hoisting 개선
  기존 var 키워드는 호이스팅이 빈번하게 일어났는데, 블록 스코프를 가진 let과 const를 추가하여 이를 방지했다.
- 화살표 문법을 지원한다.
- iterator와 generator를 지원한다.
- module의 import/export를 지원한다.
- Promise 도입
  비동기적 언어 특성상 callback 이슈가 잦았는, promise를 도입하여 이를 해결할 수 있다.