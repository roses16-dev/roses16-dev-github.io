---
layout: single
title: "[solved algorithm] 신고 결과 받기"
categories: algorithm
tags: javascript 'solved algorithm'
toc: true
sidebar:
  nav: "docs"
---

### 알고리즘 문제풀이

#### · 문제

신입사원 무지는 게시판 불량 이용자를 신고하고 처리 결과를 메일로 발송하는 시스템을 개발하려 합니다. 무지가 개발하려는 시스템은 다음과 같습니다.

- 각 유저는 한 번에 한 명의 유저를 신고할 수 있습니다.
  - 신고 횟수에 제한은 없습니다. 서로 다른 유저를 계속해서 신고할 수 있습니다.
  - 한 유저를 여러 번 신고할 수도 있지만, 동일한 유저에 대한 신고 횟수는 1회로 처리됩니다.
- k번 이상 신고된 유저는 게시판 이용이 정지되며, 해당 유저를 신고한 모든 유저에게 정지 사실을 메일로 발송합니다.
  - 유저가 신고한 모든 내용을 취합하여 마지막에 한꺼번에 게시판 이용 정지를 시키면서 정지 메일을 발송합니다.

이용자의 ID가 담긴 문자열 배열 `id_list`, 각 이용자가 신고한 이용자의 ID 정보가 담긴 문자열 배열 `report`, 정지 기준이 되는 신고 횟수 `k`가 매개변수로 주어질 때, 각 유저별로 처리 결과 메일을 받은 횟수를 배열에 담아 return 하도록 solution 함수를 완성해주세요.



#### · 풀이코드

- 시간초과로 문제 해결에 실패하여 한줄로 축소했던 코드들을 다시 풀고 반복문 안에서는 최소한의 작업만 남겨두려고 했다.

```javascript
function solution(id_list, report, k) {
    var answer = new Array(id_list.length).fill(0);
    report = Array.from(new Set(report))
    let arr_report = report.map(e => e.split(' '));

    let temp = [];
    for( element of id_list ){
        temp = arr_report.filter(e => e[1] === element);

        if(temp.length >= k ){
            temp.forEach(e => {
                answer[id_list.indexOf(e[0])] ++;
            })
        }
    }
    return answer;
}
```



#### 문제출처

> - https://school.programmers.co.kr/learn/courses/30/lessons/92334
