---
layout: single
title: "[Trouble Shooting] String 말 줄임 처리"
categories: TroubleShooting
tags: TroubleShooting
toc: true
sidebar:
  nav: "docs"
---



#### 문제

![image-20221024174231158](C:\Users\Minjoo\Desktop\devlog\roses16-dev.github.io\images\2022-10-24-Mixed_Content\image-20221024174231158.png)

```bash
Mixed Content: The page at 'https://CLIENT_URL/PATH' was loaded over HTTPS, but requested an insecure XMLHttpRequest endpoint 'http://API_URL/PATH'. This request has been blocked; the content must be served over HTTPS.
```



#### 해결

https 에서 http로 API요청을 보낼 때 발생하는 오류메세지. https로 통일하여 해결하였다.



HTML 헤더에 아래 코드를 추가하는 방식으로도 해결이 가능하다고한다.

```html
<meta http-equiv="Content-Security-Policy" content="upgrade-insecure-requests">
```

- `<meta>` : 웹 페이지의 보이지 않는 정보를 제공하는 태그
  - `name` : 
  - `http-equiv` : 
  - `charset` : 
  - `itemprop` : 

