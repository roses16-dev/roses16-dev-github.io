---
layout: single
title: "[CSS] String 말 줄임 처리"
categories: CSS
tags: CSS
toc: true
sidebar:
  nav: "docs"
---

줄을 넘어가는 string을 표시할 때 끝 부분을 ' ... ' 으로 표시하는 말 줄임 처리를 할 수 있는 코드



```CSS
p{
    white-space: nowrap;    
    overflow: hidden;
    text-overflow: ellipsis;
}
```

 

- `white-space: nowrap` 

  `white-space`는 문자열 내 공백과 개행 문자의 처리, 설정된 블록의 범위를 벗어난 Text의 개행 여부를 설정한다.

  `nowrap`은 2개 이상의 공백을 1개로 축소하고, 개행 문자를 무시하며, 범위를 벗어난 Text도 개행없이 출력한다.

  

- `overflow: hidden`

  `overflow`는 설정된 블록의 범위를 벗어난 컨텐츠의 처리를 설정한다.

  `hidden`은 범위를 벗어난 컨텐츠는 숨긴다.



- `text-overflow: ellipsis` 

  `text-overflow`는 설정된 블록의 범위를 벗어난 문자열의 처리를 설정한다.

  `ellipsis`는 문자열의 뒷 부분을 '...'으로 말 줄임 처리를 한다.

  단독으로는 말줄임 처리를 할 수 없으며 `overflow: hidden`과 함께 사용하여야 정상적으로 동작한다.

