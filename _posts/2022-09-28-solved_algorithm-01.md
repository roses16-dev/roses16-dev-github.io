---
layout: single
title: "[solved algorithm] JadenCase 문자열 만들기"
categories: algorithm
tags: javascript, solved algorithm
toc: true
sidebar:
  nav: "docs"

---

### 알고리즘 문제풀이

#### · 문제

JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)
문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.

##### 제한 조건

- s는 길이 1 이상 200 이하인 문자열입니다.
- s는 알파벳과 숫자, 공백문자(" ")로 이루어져 있습니다.
  - 숫자는 단어의 첫 문자로만 나옵니다.
  - 숫자로만 이루어진 단어는 없습니다.
  - 공백문자가 연속해서 나올 수 있습니다.



#### · 풀이코드

```javascript
function solution(s) {
    let exp = /\b[a-z]/g
    return s.toLowerCase().replace(exp, e => e.toUpperCase());
}
```

1. / 단어 시작 위치의 1자리 소문자 / 정규표현식을 만든다. 
2. 문자열 전체를 소문자로 변경한다.
3. Replce 함수로 정규표현식 값을 변경한다. 
   변경 함수는 단순한 toUpperCase() ! 



#### 문제출처

> - https://school.programmers.co.kr/learn/courses/30/lessons/12951