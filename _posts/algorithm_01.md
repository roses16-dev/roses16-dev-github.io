---
layout: single
title: "나누어 떨어지는 숫자 배열"
categories: algorithm
tag: javascript
---

https://school.programmers.co.kr/learn/courses/30/lessons/12910

배열과 정수를 받아 정수로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수 작성하기.
나누어 떨어지는 값이 없을 경우 -1을 담아 반환

```javascript
function solution(arr, divisor) {
    var answer = [];
    
    for(let i=0 ; i < arr.length ; i++){
        if(arr[i]%divisor == 0){
            answer.push(arr[i])
        }
    }
    
    if( answer.length == 0 ){
        answer.push(-1)
    } else {
        answer.sort(function(a, b){
        return a - b;
        }) 
    }
    
    return answer;
}
```