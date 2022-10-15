---
layout: single
title: "[react] json-server"
categories: react
tags: react
toc: true
sidebar:
  nav: "docs"
---

json server는 간단한 DB와 API 서버를 생성해주는 패키지이다. 📕
BE에서 실제 DB와 API 서버가 구축될때까지 FE 개발에 임시적으로 사용할 mock data를 생성하기 위해 사용한다. 
( 다만 실무에서는 FE에서 디자인 작업을 먼저 하는 동안 BE에서 DB와 API를 제공해주기때문에 쓰이는 경우가 잘 없다는 매니저님의 첨언이 있었다. )



#### 사용하기

---

- 설치 및 실행하기

  ```bash
  yarn add json-server
  ```

  ```bash
  yarn json-server --watch db.json --port 3001
  ```

  `db.json` : DB로 사용할 파일 설정. 해당 파일의 자료가 API로 전달된다.

  `--port 3001` : 사용할 포트번호 지정

  

- 자료형태

  위와같이 json을 실행하면 폴더 내 `db.json`파일이 생성된다. 해당 파일에서 기본적인 자료 형태를 알 수 있다.

  ``` json
  {
    "TABLE_NAME": [
      {
        "id": 1,
        "title": "React",
        "author": "MJ"
      }
    ]
  }
  ```

  위와 같이 작성된 자료는 `url:3001/TABLE_NAME`의 경로로 접속하여 확인할 수 있으며 javascript 내에서의 통신은 Axios 패키지로 가능하다.



- API

  GET, POST, DELETE, PATCH 등의 API를 제공한다. 보다 많은 API는 아래 문서에서 확인이 가능하다.

  https://www.npmjs.com/package/json-server





#### 출처

> - 항해99 React 3-3  강의
> - https://www.npmjs.com/package/json-server
