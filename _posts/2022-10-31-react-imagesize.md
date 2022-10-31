---
layout: single
title: "[react] Image size 접근하기"
categories: react
tags: react
sidebar:
  nav: "docs"
---









- 이미지 인스턴스로 접근하기

  ```javascript
  const image = new Image();	// image 인스턴스 생성
  image.src = '../IMAGE_PATH'	// image 경로 설정
  ```

  `image.width` : 이미지 width(px)

  `image.height` : 이미지 height(px)

