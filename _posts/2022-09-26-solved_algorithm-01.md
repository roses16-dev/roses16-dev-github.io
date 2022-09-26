---
layout: single
title: "[solved algorithm] 시저 암호"
categories: algorithm
tags: [javascript, solved algorithm]
toc: true
---



### 시저 암호

#### · 문제

어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다.
예를 들어 "AB"는 1만큼 밀면 "BC"가 되고, 3만큼 밀면 "DE"가 됩니다. "z"는 1만큼 밀면 "a"가 됩니다.
문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요.



#### · 풀이코드

- 이차원배열 사용으로 코드 요약

```javascript
function solution(s, n) {
    var answer = '';

    let arr_case = [];
    arr_case[0] = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z'];
    arr_case[1] = ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'];

    for ( [index, e] of Array.from(s).entries() ){
        // 공란은 그대로 사용
        if(e === " ") {
            answer += " ";
            continue;
        }
        // 대문자/소문자 여부에 따라 배열 선택 → index+n 값이 length를 넘어가는 경우 예외처리
        let isUpper = Number( e === e.toUpperCase() );
        let n_nextIndex = arr_case[isUpper].indexOf(e) + n;
        answer += n_nextIndex >= arr_case[isUpper].length ? arr_case[isUpper][n_nextIndex - arr_case[isUpper].length] : arr_case[isUpper][n_nextIndex];
    }
    return answer;
}
```



#### 문제출처

> - https://school.programmers.co.kr/learn/courses/30/lessons/12926