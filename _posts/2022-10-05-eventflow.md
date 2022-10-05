---
layout: single
title: "[HTML] 이벤트 전파 (Event flow)"
categories: HTML
sidebar:
  nav: "docs"
---



#### 이벤트 전파 (Event flow)

HTML은 여러 요소들이 중첩되어 쌓여있다.

```HTML
<html>
    HTML
    <body>
        BODY
        <div>
            DIV
        </div>
    </body>
</html>
```

때문에 위 태그`<html>`, `<body>`, `<div>` 에 모두 onClick Event를 설정해둔 채로 Div를 클릭했을때, HTML은 중첩된 3개의 요소들 중 우리가 실행을 원하는 것이 어떤 onClick 함수인지 판단이 어려워진다. 그래서 중첩된 요소들의 onClick 함수를 모두 실행한다.

이 때 onClick 함수가 호출되는 순서는 아래와 같이 Capture phase와 Bubble phase 두 가지로 나누어진다.

![image-20221005095224319](C:\Users\Minjoo\Desktop\devlog\roses16-dev.github.io\images\2022-10-05-eventflow\image-20221005095224319.png)

위 이미지에서 Target은 직접 클릭이 발생한 최상위 요소를 가리킨다. 이벤트가 발생하면 `event.target.nodeName`으로 해당 요소를 확인할 수 있다. 
Current target은 본인 요소를 말한다. 이벤트가 호출되었을 때 `this.nodeName`으로 확인할 수 있다.

addEventListener는 Target과 Current target이 다른 요소들에게 ( 예제에서는 BODY와 HTML이 해당한다. ) Capture phase에서 실행될지, Bubble phase에서 실행될지 직접 선택할 수 있게 한다.

```javascript
addEventListener('click', function(event){}, ___Boolean___)
```

addEventListener의 세 번째 인자로 true가 입력될 경우 Capture phase에서, false가 입력될 경우 Bubble phase에서 실행된다. default는 false이다.



#### 이벤트 전파를 제어하는 함수

- `event.stopPropagation()`  : 실행 이후의 propagation을 막는다.  단, 같은 대상의 다른 EventListener까지 막지는 않는다.
- `event.stopImmediateProgation()` :같은 이벤트에 대해 다른 EventListener를 모두 멈춘다.  같은 대상의 다른 EventListener까지도 막는다.





### 참조

> - https://www.youtube.com/watch?v=7gKtNC3b_S8