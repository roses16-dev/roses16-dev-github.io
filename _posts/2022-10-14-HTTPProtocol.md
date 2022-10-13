---
layout: single
title: "[Network] HTTP Protocol"
categories: network
tags: network
toc: true
sidebar:
  nav: "docs"

---

HTTP ( Hypertext Transfer Protocol ) 은 서버와 브라우저 간에 데이터를 주고 받기 위한 형식입니다.



#### HTTP Request & HTTP Response

---

HTTP 프로토콜은 브라우저가 서버에게 HTTP Request ( URL + Request method )를 보내면 서버에서 브라우저로 HTTP Response ( Status code + Response body )를 보내주는 방식으로 진행된다.



#### HTTP Request

---

HTTP Request에는 HTTP request method( HTTP Verbs )를 이용하며 아래와 같이 종류가 구분되어있다.

- GET : 존재하는 자원에 대한 요청
- POST : 새로운 자원을 생성
- PUT : 존재하는 자원에 대한 변경
- DELETE : 존재하는 자원에 대한 삭제
- HEAD : 서버 헤더 정보를 획득. GET과 비슷하지만 Response Body를 사용하지않는다.
- OPTIONS : 서버 옵션을 확인. [CORS ( Cross-Origin Resource )](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) 에서 사용한다.

※ POST method는 PUT과 DELETE의 동작도 수행할 수 있다.



#### HTTP Response

---

HTTP Status Code( HTTP 상태 코드 )는 서버에서 브라우저로 보내주는 응답정보 중 하나로 다양한 코드가 사용되며 주요한 코드는 아래와 같다.

- 200번대 : 성공
  - 200 : GET 요청에 대한 성공
  - 204 : No Content. 성공했으나 응답 본문에 데이터가 없음
  - 205 : Reset Content. 성공했으나 클라이언트의 화면을 새로 고침하도록 권고
  - 206 : Partial Content. 성공했으나 일부 범위의 데이터만 반환
- 300번대 : Redirection. 브라우저가 이전 주소로 데이터를 요청하여 서버에서 새 URL로 redirect를 유도하는 경우
  - 301 : Moved Permanently. 요청한 자원이 새 URL에 존재
  - 303 : See Other. 요청한 자원이 임시 주소에 존재
  - 304 : Not Modified. 요청한 자원이 변경되지 않았으므로 클라이언트에 캐싱된 자원을 사용하도록 권고
- 400번대 : Client error. Request코드가 잘못된 경우. 유효하지 않은 자원을 요청했거나, 요청이나 권한이 잘못된 경우
  - 400 : Bad Request. 잘못된 요청
  - 401 : Unauthorized. 권한 없이 요청. Authorization 헤더가 잘못된 경우
  - 403 : Forbidden. 서버에서 해당 자원에 대해 접근 금지
  - 404 : 요청한 자원이 서버에 없음
  - 405 : Method Not Allowed. 허용되지 않은 요청 메서드
  - 409 : Conflict. 최신 자원이 아닌데 업데이트하는 경우
- 500번대 : Server error
  - 501 : Not Implemented. 요청한 동작에 대해 서버가 수행할 수 없는 경우
  - 503 : Service Unavailable. 서버가 과부하 또는 유지 보수로 내려간 경우



#### 출처

> - https://joshua1988.github.io/web-development/http-part1/