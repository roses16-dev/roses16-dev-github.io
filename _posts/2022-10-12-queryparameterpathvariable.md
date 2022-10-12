---
layout: single
title: "[ETC] Path variable & Query string & Query parameter"
categories: ETC
toc: true
sidebar:
  nav: "docs"
---

GET 방식으로 url을 통해 데이터를 전송하는 방법들에 대한 정리 📕



#### Query parameter ( Query string )

---

경로 뒤에 입력 데이터를 함께 전송한다.

 `?` : 데이터의 시작

`key=value` : 데이터 형태

`&` : 이후 데이터가 더 있다는 의미

```
naver.com/search?where=nexearch&query=redux
→ naver.com/search 경로에 { where: nexearch, query: redux } 데이터를 전달한다.
```



#### Path variable

---

경로를 변수로 사용한다.

```
blog.naver.com/nickname/232323
 → blog.naver.com/nickname 경로에 232323 데이터를 전달한다.
```

