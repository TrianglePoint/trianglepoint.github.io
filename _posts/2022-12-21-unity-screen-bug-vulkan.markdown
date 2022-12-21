---
layout: post
title:  "Unity에서 화면 렉, 버벅임, 그 후 앱이 종료되는 문제"
date:   2022-12-21 18:58:00 +0900
categories: Unity
---
Andorid 타겟으로 개발중인 Unity 게임 테스트중에 LG G7 thinkQ에서 특정 기능을 실행시 화면이 굳어버리는 문제가 발생.<br />
소리도 잘 나오고 조작도 잘 되지만 화면은 굳어버린 시점의 한두 개의 프레임을 반복해서 재생.<br />
(Unity 버전을 2019 -> 2021로 변경하고 발생)<br />

해당 기기를 직접 디버깅을 못하는 상황이였지만<br />
다행히 [Play store console][psc]을 통하여 업로드를 한 APK라서 상세한 오류 내용을 확인 가능하였다.<br />
종류가 메모리 영역 침범이었나 그랬는데, 스택 트레이스에 vulkan이라는 단어가 보였다.<br />

조사한 내용을 참고하여 Unity의 Player setting - Player - Other setting에서 `Vulkan`이라는 그래픽 API를 제거하니 해결.<br />
(OpenGL~이라는 API가 있어서 제거해도 문제 없었음)<br />

Vulkan은 보통 3D 그래픽에서 사용한다니 현재 프로젝트와는 관계없음.<br />
배포시에 지원 기기에서도 변경점 없었으니 괜찮을듯.

[psc]: https://play.google.com/console/