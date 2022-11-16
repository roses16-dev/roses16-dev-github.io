---
layout: single
title: "[Error] Mac AUto import Error"
categories: Error
tags: Error
sidebar:
  nav: "docs"
---



- **⛔ Error** 

  ```
  ERROR in ./node_modules/hoist-non-react-statics/node_modules/react-is/index.js
  Module build failed (from ./node_modules/source-map-loader/dist/cjs.js):
  Error: ENOENT: no such file or directory, open '/Users/h****e/Desktop/FrontEnd/node_modules/hoist-non-react-statics/node_modules/react-is/index.js'
  ERROR in ./node_modules/mime/lite.js
  Module build failed (from ./node_modules/source-map-loader/dist/cjs.js):
  Error: ENOENT: no such file or directory, open '/Users/h****e/Desktop/FrontEnd/node_modules/mime/lite.js'
  ERROR in ./node_modules/uuid/dist/esm-browser/index.js
  Module build failed (from ./node_modules/source-map-loader/dist/cjs.js):
  Error: ENOENT: no such file or directory, open '/Users/h****e/Desktop/FrontEnd/node_modules/uuid/dist/esm-browser/index.js'
  ```

  Mac에서만 발생했던 오류로 file or directory를 찾을 수 없다는 메세지가 나타나는데 실제로 해당 file/directory는 존재하지않고 따로 import를 설정해 두지도 않았다. 

  

-  **✔ Clear**

  찾아보니 Mac에서는 종종 이상한 경로로 Auto import가 작동하는 일이 있다고한다. 출처에서는 다양한 해결 방법을 제시해주셨으나 우리 프로젝트에서는 터미널을 껐다 다시 켜는 것으로 해결되었다.



- **📌 Refer **

  [Dotorimook's blog](https://dotorimook.github.io/post/2021-10-14-auto-import-error/)



