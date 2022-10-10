---
layout: single
title: "[javascript] 예외처리 Exception handling"
categories: javascript
tags: javascript basic study exception_handling
toc: true
sidebar:
  nav: "docs"
---

"혼자 공부하는 자바스크립트" 스터디 모임 정리 노트 입니다. 📚



#### 구문오류와 예외

---

- **오류의 종류**

  - 구문오류 ( syntax error )
    프로그램 실행 전에 발생하는 오류. 괄호가 닫히지 않았은 등 구문의 형태가 잘못되어 프로그램이 작동하지 않는 경우.


  - 예외 ( exception ) & 런타임 오류 ( runtime error )
    프로그램 실행 후에 발생하는 오류. syntax error를 제외한 모든 오류 ( type error, reference error, range error )가 분류된다.


- **기본 예외 처리** 
  조건문 IF를 사용하여 예외가 발생하지 않게 만드는 것.

- **고급 예외 처리** 
  `try catch finally` 구문으로 예외가 발생했을 때의 처리를 지정하는 것.

  ```javascript
  try{
      // 실행할 코드
  } catch (exception) {
      // try에서 오류가 발생하면 실행할 코드
  } finally {
      // try 또는 catch가 실행이 완료된 후 반드시 실행되는 코드
  }
  ```

  ※ `finally` 구문은 `catch` 또는 `try`에서 `return`으로 함수를 종료시키더라도 실행된다.



#### 예외 처리 고급

---

- **예외 객체 ( exception object )**

  `catch(exception)` 구문에서 받아오는 매개변수 `exception`를 말한다.

  - `exception.name` : 예외 이름 
  - `exception.message` : 예외 메세지

  ![image-20221010112749496](\images\2022-10-08-study-exceptionHandling\image-20221010112749496.png)

  - `Uncaught ReferenceError` : 예외 이름 
  - `abc is not defined` : 예외 메세지

- **예외 강제 발생**

  예외를 강제로 발생시킬 수 있는 코드. 예외를 발생시키므로 `throw`코드가 실행되면 프로그램이 중단된다.

  ```javascript
  throw '문자열'						// Uncaught 문자열
  throw new Error('문자열')			// Uncaught Error: 문자열 at 파일 이름:줄 번호
  ```

  클라이언트가 의도하지 않은 방식으로 프로그램을 사용할 때 Error문구를 출력 프로그램을 중단시킬 수 있다.
