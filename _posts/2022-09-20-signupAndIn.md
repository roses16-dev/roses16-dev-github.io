---
layout: single
title: "[javascript] Sign up & Sign in"
categories: javascript
tags: javscript python
toc: true
sidebar:
  nav: "docs"
---

javascript와 python으로 만드는 Sign up & Sign in



#### 개요

---

##### · 해시함수

일종의 암호화 알고리즘

항상 똑같은 길이의 암호화값 만든다.
입력값이 조금만 바뀌어도 완전히 다른 암호화값을 만든다.
암호화값으로 입력값을 유추할 수 없다.



##### · JWT (json web token)

json을 통한 정보전달방식
로그인 유지 기능 구현 시 사용하며, 이 때 토큰에는 ID와 로그인 유효시간이 전달된다.



##### · Cookie

~~너를 위해 구웠지~~
클라이언트 브라우저에 임시로 저장되는 정보.
딕셔너리 { Key:Value } 형태.

- 클라이언트(JavaScript)에서 Save & Delete

  ```javascript
  $.cookie('mytoken', response['token']);
  // $.cookie(Key, Value)
  
  $.removeCookie('mytoken');
  // 쿠키지우기. Logout 할 때 사용한다.
  ```

- 서버(Python)에서 Read

  ```python
  request.cookies.get('mytoken')
  # request.cookies.get(Key)
  ```

- 쿠키확인하는 법
  브라우저 DevTool > Application > Cookies



#### 만들기

---

- 회원가입

  1) form 입력값 체크
     정규표현식 이용

     ```javascript
     // 예시
     function is_nickname(asValue) {
        var regExp = /^(?=.*[a-zA-Z])[-a-zA-Z0-9_.]{2,10}$/;
        return regExp.test(asValue);
     }
     
     function is_password(asValue) {
         var regExp = /^(?=.*\d)(?=.*[a-zA-Z])[0-9a-zA-Z!@#$%^&*]{8,20}$/;
         return regExp.test(asValue);
     }
     ```

     

  2) ID중복체크
  3) PW암호화 / hashlib이용
  4) DB 저장

- 로그인

  1) form 입력값 체크
     불필요한 DB 접속차단 / 일반적으로 단순 공란 체크만으로도 충분

  2) PW 복호화 / hashlib이용

  3) DB 검색 및 ID/PW 정보 일치 체크

  4) 서버:Token{ ID, 유효기간 } return 클라이언트:Token을 Cookie로 저장

     ```python
     payload = {
     'id': username_receive,
     'exp': datetime.utcnow() + timedelta(seconds=60 * 60 * 24) 
     # 로그인 24시간 유지
     # datetime.utcnow() : 그리니치 표준 기준 현재시각
     # datetime.cnow()   : 현재 로케이션 기준 현재시각
     # timedelta(days=1, hours=1, minutes=1) 
     # : 기간 또는 시간을 표현하는 함수. 인자로 위와같이 주, 일, 시, 분, 초, 밀리 초, 마이크로 초를 받는다. 
     }
     ```

     

  