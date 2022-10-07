---
layout: single
title: "[CSS] Reset & Normalize"
categories: CSS
tags: CSS
toc: true
sidebar:
  nav: "docs"
---



#### CSS Reset, Normalize가 만들어진 이유

브라우저는 저마다 고유의 기본 서식 ( User-Agent StyleSheet )을 가지고 있다.

> Chrome의 기본 서식 
> https://chromium.googlesource.com/chromium/src/third_party/+/master/blink/renderer/core/html/resources/html.css

때문에 브라우저마다 작성한 웹 사이트가 다르게 표시될 수 있어 브라우저들의 스타일을 하나로 통일하는 선행 작업이 필요했고, 이것이 CSS Reset과 Normalize이다.



#### CSS Reset

`*` Selector를 이용하여 CSS를 초기화 할 경우 성능과 출력에 이슈가 있어 조금씩 정교하게 CSS를 만들어나가며 여러 버전의 Reset이 탄생했고, 그 중 에릭마이어의 CSS Reset이 가장 유명하며 아직까지도 쓰이고 있다.

> 에릭마이어의 CSS Reset Site, CSS Reset 전문을 확인할 수 있다.
> https://meyerweb.com/eric/tools/css/reset/



#### Normalize

이후 User-Agent StyleSheet에 표준이 생겼으나, 여전히 모든 브라우저간의 차이는 존재했다. 이 차이를 표준 브라우저 스타일로 동일하게 보일 수 있는 정규화가 Normalize이다. 



> normalize CSS git, 지속적으로 업데이트 된다.
> https://github.com/necolas/normalize.css

> Styled Componenets의 normalize
> https://www.npmjs.com/package/styled-normalize



#### Opinionated Normalize

표준 스타일에서 더 나은 값으로 Default Style을 만드는 방법

> Bootstrap용 Opinionated Normalize
> https://github.com/twbs/bootstrap/blob/45eb70e03c1905d247c6e012fff9e263d1326066/scss/_reboot.scss



#### Modern CSS Reset

최소한의 CSS Reset과 기본보다 나은 스펙을 Default로 만들어주는 형태

**Default로 쓰일 수 있는 코드**

- `box-sizing: border-box` : border를 box의 inner로 처리한다는 의미이다. 
- `table { border-collapse: collapse` : 셀과 테두리의 간격을 처리하는 방법, `collapse` 는 병합한다는 의미이다.

> 예시사이트 
> https://github.com/jgthms/minireset.css



#### 출처

> - https://velog.io/@teo/2022-CSS-Reset-%EB%8B%A4%EC%8B%9C-%EC%8D%A8%EB%B3%B4%EA%B8%B0