---
layout: single
title: "[LookBack] 라이어게임 : 비밀의 문"
categories: LookBack
toc: true
sidebar:
  nav: "docs"
---

< 라이어게임 : 비밀의 문 > 프로젝트 회고



### 💻 개요

---

- 개발 기간 : 2022.11.04~2022.12.16 ( 6주 )
- 사용 기술 : Javascript, React, Redux, SCSS, Axios, SockJS, Stomp, WebRTC, Open-vidu, AWS Amplify
- 발표영상 : https://youtu.be/et2UZDITnOs



### 📚 경험

---

- **팀장**으로써 전반적인 업무 리딩 및 회의 주도
- 시범 서비스를 통해 생성된 **게임 방 669개, 회원 239명, 플레이된 게임 657판, 모든 유저 전체 플레이 약 30시간, 36건의 피드백 수집** 및 반영/개선 경험
- 디자인 팀, 백엔드 팀과의 협업 경험
- Github Issue, Projects, Pull requests 등 **Issue tracker를 이용한 협업** 경험
- AWS Amplify를 이용한 자동배포
  - **Git Actions와 AWS**를 이용한 자동배포도 경험하였으나 최종 사용되지않음
- 라이어 게임 웹으로 구현
  - SockJS와 Stomp를 이용한 **소켓 통신**으로 게임 룰 구현
  - WebRTC를 이용하여 **화상 채팅 연결** 및 게임 룰에 따른 Device 제어 구현
- Sentry를 이용하여 user side error log 실시간 수집 및 개선



### 💬 회고

---

#### 좋았던 점

- 공부를 시작하며 만난 Javascript와 React의 코드들은 대부분 멘토님들께서 프로젝트에 알맞은 형태로 준비해주신 예제 코드들 이었는데,
  webRTC와 WebSocket을 알아가며 Google과 Github 등에서 만난 코드는 새롭고 당황스럽고 많은 부분이 내 프로젝트와는 달라 짜집어 고쳐가며 만들어야 했다.
  덕분에 앞으로 새로운 기능이 주어지더라도 배우면 할 수 있겠다. 라는 무던한 마음이 생겼다.
- Git issue, projects, PR을 조금은 잘 썼던 프로젝트였다.
- 성실하고 귀여운 팀원들을 만나 즐겁게 일할 수 있었다. ❤



#### 아쉬운 점

- redux, redux-toolkit 등 배운 기능의 능숙한 사용을 보여 주지는 못한 기획이었다. 
- open-vidu에서 제공한 소스가 class component로 작성된 코드였는데 이를 100% 활용하지 못했다. 시간이 넉넉했다면 전체 코드를 function component로 만드는 작업을 더 시도해보았을 것 같다.
- 유저 사이드에서 발생한 모든 버그를 해결하지 못했다. 왜 문제가 발생했는지, 어떤 케이스에서 발생한 문제인지 자세히 알고 싶고, 어떤 예외처리를 추가했어야했는지는 아직도 고민이 된다.
- Typescript를 써보고 싶었다. 😥





다음은 혼자 작성하는 side project를 만들어볼 예정이다.
DB는 간단한 json-server로 운영하고 필요하다 판단되는 경우 MySQL과 node.js 서버를 만들어 돌려야겠다. 

자세한 기획은 이후에 나오겠지만 Typescript를 경험해보고, 이번 프로젝트보다 개선된 scss 구조를 만들어보고, 칸반보드 기능을 넣은 프로젝트가 될 것 같다.