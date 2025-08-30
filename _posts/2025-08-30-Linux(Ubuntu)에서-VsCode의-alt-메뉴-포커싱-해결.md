---
layout: post
title:  "Linux(Ubuntu)에서 VsCode의 alt 메뉴 포커싱 해결"
date:   2025-08-30 10:26:00 +0900
categories: Linux
---

> Windows11에서는 발생 안 하는 문제라, 비교하며 작성함.

# 문제
* VsCode에서 한글 입력 중(포커스가 한글 칸)에 우측 `alt`(한영키로 지정함)를 누르면 메뉴 포커싱.
* (Windows11: 문제 없음: 좌측 `alt`만 메뉴 포커싱)

# 원인
* 설정이 아래와 같을 때 발생:
    * [window.titleBarStyle](vscode://settings/window.titleBarStyle): `custom`
    * [window.customMenuBarAltFocus](vscode://settings/window.customMenuBarAltFocus): `true`
* (Windows11: 위 설정으로 되어있음)

# 해결
* 2가지 방법 중 선택.
1. [window.titleBarStyle](vscode://settings/window.titleBarStyle)를 `native`로 한다.
    * 메뉴 바가 OS 고유 형태로 표시. 상단 검색창과 분리.
    * 좌측 `alt`만 메뉴 포커싱.
2. 'window.titleBarStyle'는 `custom`으로 유지, [window.customMenuBarAltFocus](vscode://settings/window.customMenuBarAltFocus)를 `false`로 지정.
    * 메뉴 바와 상단 검색창이 통합.
    * 양측 `alt`가 메뉴 포커싱 비활성화.
    * (필자는 이걸로 함: 공간 효율 좋고, 메뉴 포커싱은 평소에 안 씀)

# 참고
* [답변: custom으로 설정, alt focus 끄기](https://stackoverflow.com/questions/48044429/override-alt-to-toggle-menu-bar-on-vs-code#answer-60282880)
    * [공식 문서: 메뉴 포커싱 끌 수 있음](https://code.visualstudio.com/updates/v1_36#_disable-alt-key-focus-of-the-custom-menu-bar)
        * (2019년인데, 왜 나는 최근에 발생했는가? 앱 설치는 이 이후인데)
    * [관련 이슈](https://github.com/microsoft/vscode/issues/84227)
* [Electron 이슈인듯](https://github.com/electron/electron/issues/34211)
