---
layout: single
title: "[react] Axios catsh Error message"
categories: react
tags: react
sidebar:
  nav: "docs"
---



try & catch 문에서 error 메세지 출력하기

```javascript
  const func = () => {
    try {
      const { data } = axios.post('<API_URL>');
    } catch (error) {
      alert(error);
    }
  }
```

위와 같이 출력했을 때 `alert(error)`에는 axios의 기본 오류 메세지가 출력된다.

![image-20221124014604043](\images\2022-11-24-axios_error_msg\image-20221124014604043.png)





네트워크에서 확인하면 아래와 같이 Backend에서 전달해준 문구가 있음에도 위와같은 메세지가 출력된다.



![image-20221124014649458](\images\2022-11-24-axios_error_msg\image-20221124014649458.png)



BE에서 전달해준 메세지를 사용하려면 `error.response` 객체를 호출하여 사용한다.

```javascript
  const func = () => {
    try {
      const { data } = instance.post('<API_URL>');
    } catch (error) {
      alert(error.response.data.statusMsg);
    }
  }
```

