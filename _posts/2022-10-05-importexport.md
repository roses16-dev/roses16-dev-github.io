---
layout: single
title: "[javascript] import & export"
categories: javascript
tags: javascript module
toc: true
sidebar:
  nav: "docs"

---

import와 export는 javascript module을 내보내고 가져오는 기능이다.



#### Module

module은 별도의 파일로 분리하여 관리하는 코드를 말한다.
일반적으로 기능별로 파일을 분리하여 관리하며 이로 인해 코드의 가독성이 좋아지고, 재사용 및 유지보수에 용이하다는 장점이 있다.

코드가 module로서 정상적으로 작동하려면 독립적인 스코프를 가져야한다. 이는 module이 import한 파일의 동작에 의도하지 않은 영향을 미치는 일을 방지한다. 문제의 예로는 변수명, 함수명의 중복사용 등이 있다.



#### Import & Export

- **Import**

  외부 파일로부터 모듈을 가져올 때 사용한다.

  ```javascript
  import { 모듈이름 } from '파일경로'
  import { 모듈이름1, 모듈이름2... } from '파일경로'
  ```

  위와 같이 하나의 파일에서 단수 혹은 다수의 모듈을 가져올 수 있다.

  

  ```javascript
  import { 원래의모듈이름 as 변경할모듈이름 } from '파일경로'
  ```

  모듈의 이름을 다르게 가져올 수 있다.

  

  ```javascript
  import * as 가져올이름 from '파일경로'
  가져올이름.모듈명()	
  ```

  다수의 모듈을 한번에 가져오길 원할 때 사용한다.

  

- **export ( named export )**

  작성한 함수/변수/클래스를 모듈로 내보낸다. 

  ```javascript
  export { 함수명 }
  export { 함수명1, 함수명2, 변수명1 as 모듈명 } 
  
  export function 함수명() { }
  export const 함수명 = () => { }
  ```

  단수 혹은 다수의 모듈을 내보낼 수 있고, aliasing ( `as` )을 통해 실제 함수명과 내보낼 모듈명을 다르게 설정할 수 있다.

  export와 선언을 같이 작성할 수도 있다.

  

- **export default ( default export )**

  일반적으로 파일에 모듈이 하나 뿐일 때 설정한다. import 시 중괄호 `{}`사용을 생략할 수 있고 모듈이름을 다르게 사용해도 가져오는데에 문제가 없다.

  ```javascript
  export default 함수명
  export { 함수명 as default}		// 두가지 export 모두 동일한 결과
  
  import 가져올이름 from '파일경로'
  ```

  export와 선언을 함께 할 때 식별자를 설정하지 않아도 된다.

  ```javascript
  export default function() { }
  export default 'String value'
  ```



찾아보았던 문서에서는 default export 사용을 지양하라는 의견도 있었다. 

import 시 임의의 이름으로 정할 수 있어 가독성이 떨어지고 IDE에서 모듈이름을 읽어오지 못해 사용상의 불편함도 있다고 한다.



#### 참조

> - https://nuhends.tistory.com/80