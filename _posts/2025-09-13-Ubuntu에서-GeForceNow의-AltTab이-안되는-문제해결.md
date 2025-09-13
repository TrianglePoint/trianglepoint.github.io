---
layout: post
title:  "Ubuntu에서 GeForceNow의 AltTab이 안되는 문제해결"
date:   2025-09-13 22:41:00 +0900
categories: Linux
---

# 상황
* 어느 날 'GeForce Now'를 키자 'inhibit shortcuts' 어쩌구 하는 권한 확인 창이 뜸.
* Allow 하고 난 후, 게임 플레이 중에 내 PC상의 `Alt+Tab`이 안됨.

# 해결
* 요약: 권한을 찾아서 거부하도록 변경.
* 아래 명령어 입력: 권한이 어디있는지 확인.
``` bash
flatpak permissions
```
* 결과: 아래처럼 `shortcuts-inhibitor`가 `GRANTED`로 되어있다면 이게 원인.
``` bash
Table Object              App                    Permissions Data
gnome shortcuts-inhibitor microsoft-edge.desktop GRANTED     0x00
```
* 아래 명령어 같이 입력(`flatpak permission-set`): 권한을 `DENIED`로 해서 끔.
``` bash
flatpak permission-set (Table명) (Object명) (App명) DENIED
```
* 으로 해야하니 내 경우는 아래를 입력.
``` bash
flatpak permission-set gnome shortcuts-inhibitor microsoft-edge.desktop DENIED
```
* 다시 `flatpak permissions`로 보면 `DENIED`로 바뀐 것을 확인 가능.
``` bash
Table Object              App                    Permissions Data
gnome shortcuts-inhibitor microsoft-edge.desktop DENIED      0x00
```
* 'GeForce Now'창을 다시 열면 해결. 끝.

# 참고
* [가상 머신 관련 질문](https://askubuntu.com/questions/1488341/how-do-i-inhibit-shortcuts-for-virtual-machines)
