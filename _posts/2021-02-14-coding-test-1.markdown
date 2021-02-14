---
layout: post
title:  "Coding test-1: 완주하지 못한 선수"
date:   2021-02-14 21:53:00 +0900
categories: Coding test
---
Programmers의 [해당 문제][programmers].<br />
각각 n개, n-1개의 list가 있는데, n개 list에는 있지만 n-1개 list에 없는 단 하나의 item를 찾는 문제다.

1. List에서 item과 일치하는 갯수를 return하는 getCount 함수를 만들어서, 갯수가 같으면 '끝냈다'라는 list에 item을 넣어두고 다음 item이 중복되면 하지않는다. <br />
갯수가 다르다면 답을 찾은 것.

2. 1번에서 '끝냈다' list를 지우고, getCount 함수에서 갯수를 셀때마다 갯수를 센 item을 지운다.<br />
그러면 반복할수록 list의 총 갯수는 줄어들겠지.

3. 찾아보니 sort하면 좋다고한다. sort한다면 getCount 함수에서 갯수를 셀때마다 갯수를 센 item을 지우는 과정은 필요가 없다.<br />
우선 sort, 그 후에 갯수 비교. 갯수 비교할때 시작 index를 매개변수로, 마지막 일치하는 last index를 return한다.<br />
그렇게하면 최악의 경우에도 list하나를 다 돌면 끝난다.

4. 다른 사람의 풀이 보기를 했다. `두 list는 단 한 자리만 제외하고 전부 일치`한다는 걸 이용해서, list 처음부터 본다는 것이다.<br />
sort는 되어있기때문에 두 item이 다르다면 n개 list쪽의 현재 item이 답이다...

코딩 테스트는 프로그래밍적인 연습이 된다고하여 해봤다.<br />
처음에 정확성 100%! 하지만 효율성은 0? 20%? 였던거같다.<br />
다른 사람의 풀이를 보니 내가 평소에 하지않던 접근 방식이었다.<br />
최상단의 코드를 두고 동의, 비판하는 의견들이 상당히 많았다.<br />
비판하는 내용에서는 "for in 대신 for (int i = 0... 쓰세요" 같은 내용이나 다른 것들.

Programmers 코딩 테스트의 효율성이란건 처리속도인것 같은데, 문법을 선택하는건 고려하지않은 것 같다.<br />
어떤 분이 말씀하셨는데, "이 문제만을 위한 코드같다, 확장성이 없다"였다.<br />
동의, 그 코드는 깔끔해서 좋았지만 일반적으로 보았을때 성능 하강하는 부분은 있긴했다.<br />

오랜만에 뇌가 살아있다고 느꼈지만, 이 사이트로 계속 해야하나 고민이다.<br />
[LeetCode][LeetCode]라는 곳도 좋아보이는데.<br />
듀오링고하는 것처럼 프로그래밍도 매일매일 할 수 있으면 좋겠다.

[programmers]: https://programmers.co.kr/learn/courses/30/lessons/42576
[leetCode]: https://leetcode.com/