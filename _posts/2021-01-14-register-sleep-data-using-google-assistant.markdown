---
layout: post
title:  "Google assistant를 이용하여 수면 시간 기록하기-1"
date:   2020-01-14 23:25:50 +0900
categories: IOT assistant
---
`Google assistant`를 사용하여 수면 시간을 등록하고 싶다.

최근 IOT에 관심이 생겨 리모컨 기능을 지원하는 장치를 구입했다. 잘자라고 하면 불을 꺼주고 다녀왔다고 하면 불을 켜준다. 
WOL도 하고싶어서 연결했다. 컴퓨터를 켜달라고하면 컴퓨터가 켜진다.

수동으로 기록하고있는 수면시간도 자동으로 하면 좋겠다. "잘자"와 "좋은 아침" 루틴으로 수면 시간을 자동으로 기록하는 것이 목표다.

[Dialogflow][dialogflow-docs]로 음성을 분석하여, `back-end`에서 처리. `Oauth`라는 인증방식으로 api권한을 사전에 취득할 필요가 있다.

[dialogflow-docs]: https://cloud.google.com/dialogflow/docs
