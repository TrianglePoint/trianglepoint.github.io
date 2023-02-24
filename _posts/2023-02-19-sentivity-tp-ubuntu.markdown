---
layout: post
title:  "Ubuntu에서 Trackpoint의 감도를 빠르게 하기"
date:   2023-02-19 01:14:00 +0900
categories: Linux
---
오른쪽 어깨, 팔, 손목이 아픈게 잘못된 마우스 자세라고 생각해서 이리저리 헤메다가 찾게된 [Trackpoint keyboard 2][tpkey2].<br />
이제 2주정도 되었는데, 평일을 반복하며 커져가던 고통이 사그라들었다. 최대 감도로 하니 부담도 적다.<br />
Windows에서는 OS + 키보드 드라이버 로 감도를 설정했지만 Ubuntu(Ubuntu 22.04.1 LTS)에서는 공식 드라이버가 없다!<br />
(드라이버가 맞는지 모르겠는데 제조사가 지원하는 프로그램이 linux계열에서는 없나보다...)<br />

xinput은 xWayland라는 것 때문에 안되고(가상 디바이스만 뜨고 실제 디바이스에는 접근이 불가능하다고 함)<br />
xset이라는 걸로 마우스 속도를 높여봐도 변화가 없어서 재부팅을 했는데 갑자기 빨라졌다!<br />

어디서 놓친걸까? 어떤 방법으로 적용되었는지 모르겠다. 위 방법 이외에도 여러가지를 시도했었는데, 그 중의 한 가지가 재부팅을 해야 적용되는 것 같다.<br />
우선은 xset이 맞다고 친다면, `xset m`으로 마우스 속도를 조정하고 재부팅을 하면 해결이 된다.<br />

나중에 새로 설정할 때를 위해서 남겨둔다.

[tpkey2]: https://www.lenovo.com/us/en/p/accessories-and-software/keyboards-and-mice/keyboards/4y40x49493