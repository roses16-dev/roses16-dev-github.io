---
layout: single
title: "[javascript] 태그드 템플릿(Tagged template)"
categories: javascript
tags: javascript basic
toc: true
sidebar:
  nav: "docs"
---

템플릿 리터럴과 태그드 템플릿 정리



### 템플릿 리터럴 ( template literal )

표현식을 허용하는 문자열 리터럴
문자열 선언 시 백틱 (` `` `) 을 사용하며 표현식은 `${}` 로 표현한다.

```javascript
let a = 'apple'
let b = 'banana'
console.log(`a: ${a}, b: ${b}`)		// 결과값 : 'a: apple, b: banana'
```

위와 같이 변수 뿐 아니라 함수, 연산의 결과를 문자열 중간에 삽입할 수 있다.



### 태그드 템플릿 ( tagged template )

템플릿 리터럴은 변수 및 결과값을 그대로 대입하기 때문에 조건에 따라 다른 값을 대입하는 것이 어렵다. 이를 보완하기 위해 중간처리 함수를 통해 표현식의 값을 조건에 따라 변경할 수 있도록 하는 것이 태그드 템플릿이다.

```javascript
function taggedTest(string, ...exp){  // string 은 템플릿 리터럴의 문자열 부분을 배열로 전달받는다.
    // 실행할 함수                     // ...exp 은 템플릿 리터럴의 표현식 부분을 배열로 전달받는다.
    return '문자열'                    // return 값은 함수 호출 부분의 `템플릿리터럴` 부분으로 반환된다.
}

console.log(taggedTest`템플릿 리터럴${변수사용}`)		// 이와 같이 호출한다. 템플릿 리터럴의 요소들은 모두 함수의 매개변수 값으로 입력된다.
// console 출력값 : '문자열' → return 값이 기존 `` 기재한 내용을 모두 대체한다.
```



함수에 조건식을 넣어 사용한 예시

```javascript
function taggedF(str, ...exp){
    let temp ='';

    for(let i = 1 ; i < str.length ; i++){
        if(i < str.length -1)     // 마지막 ${feel} 표현식을 제외한 부분에만 'red' 글자를 넣어주기 위해 사용했다.
            temp += 'red' + str[i]
    }
    
    if(feel === 'sad') return 'I Hate ' + temp
    if(feel === 'joy') return 'I Love ' + temp
}

let str = ''
let feel ='joy'
console.log(taggedF`${str} apple, ${str} shoes. ${feel}`)
// console 출력값 : 'I Love red apple, red shoes.'
```



### 참조

> - https://blogpack.tistory.com/610
> - https://www.youtube.com/watch?v=4oVJVglLLns
