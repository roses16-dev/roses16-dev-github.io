---
layout: single
title: "[CSS] 마진 병합 ( Margin collapsing )"
categories: CSS margin_collapsing
toc: true
sidebar:
  nav: "docs"


---

### CSS Margin collapsing ( 마진 병합, 마진 붕괘 ) 

#### 마진 병합 현상

```CSS
.box {
    width:150px;
    height:150px;
    margin: 20px;  /* 상, 하, 좌, 우 여백 모두 20px*/
    border: 1px solid;
}
```

```HTML
<body>
    <div class='box'>A</div>
    <div class='box'>B</div>
</body>
```

위 예제와 같이 상, 하, 좌, 우의 여백을 모두 가진 두 DIV 태그를 출력한 결과물은 아래와 같다.

![image-20221003201230343](\images\2022-10-03-css-margin-collapsing\image-20221003201230343.png)

두 DIV의 margin이 모두 20px 이라면 A DIV와 B DIV 사이 간격이 40px이어야하지만, CSS는 의도적으로 두 마진값을 하나로 병합하여 균일한 정렬에 도움을 주는데 이를 마진병합 이라고 말한다.
※ 병합 시에는 두 마진 중 큰 값으로 병합한다.

마진병합이 일어나는 조건은 아래와 같다. 

- 인접해있는 Block 요소끼리만 일어난다.

- 상/하단만 해당하며 좌/우는 발생하지 않는다.

  

#### 문제점

마진 병합의 문제는 주로 부모와 자식 DIV 간에 발생할 때 나타난다.

```css
.wrap-box{
    width: 250px;
    height: 250px;
    background-color: papayawhip;
}
.box {
    width:150px;
    height:150px;
    margin: 20px;  /* 상, 하, 좌, 우 여백 모두 20px*/
    border: 1px solid;
}
```

```html
<div class='wrap-box'>
    <div class='box'></div>
</div>
```

위 예제와 같이 box DIV를 다른 DIV안에 담았을 때의 결과값은 아래와 같다.

![](\images\2022-10-03-css-margin-collapsing\image-20221003221804462.png)

margin-top 부분에서 마진 병합이 발생했다.
부모 DIV에는 주지 않은 여백이 발생했고, 자식 DIV는 가져야할 마진이 부모DIV 바깥쪽의 마진과 병합되어 나타났다.

이를 해결하는 방법으로는 부모 DIV에 1px이라도 값을 주는 것이다.
부모 DIV에 값이 들어가거나, 아래와 같은 속성으로 px단위 값을 주면 해결된다.

- Border
- Padding
- overflow:hidden

![image-20221003223656662](\images\2022-10-03-css-margin-collapsing\image-20221003223656662.png)



#### 참조

> https://www.youtube.com/watch?v=c19Mjg-ivxc