---
layout: post
title:  "Google assistant를 이용하여 수면 시간 기록하기-2"
date:   2021-01-16 16:55:00 +0900
categories: IOT assistant
---
[Dialogflow][dialogflow-docs]가 back-end와 통신하는 방식으로 한다고 저번 글에 적었다.
REST방식API.. 

[firebase][firebase-main](아니면 google project인가?)를 이용하여 google 계정으로부터 oauth인증을 받아서, post 요청으로 해당 google 계정의 fit 저장소에 수면 시간을 기록한다.

위 기능이 확인되면 dialogflow를 사용해서 대신 처리할 수 있도록 한다. 그러면 끝이지만 rest요청을 로컬에서 간단하게 보낼 수도 없을정도로 하는 방법을 잊어버렸다.

우선 뒤쪽부터 진행해야겠다.

[dialogflow-docs]: https://cloud.google.com/dialogflow/docs
[firebase-main]: https://firebase.google.com/
