---
layout: post
title:  "Bundle의 Ruby없음 문제 해결"
date:   2025-08-20 21:29:00 +0900
categories: Linux
---
좋아, 새로운 문제다.

* Jekyll 블로그를 돌리기 위해 bundle를 쓰는데 아래 에러 발생.
``` cmd
> bundle
/usr/bin/env: ‘ruby3.0’: No such file or directory
```
* [이 답변](https://stackoverflow.com/questions/77998194/usr-bin-env-ruby3-0-no-such-file-or-directory#answer-79595614)에 의하면 bundle의 ruby 값이 잘못되었다고함. `/usr/local/bin/bundle`을 편집. (vi로 함)

```
# Before
#!/usr/bin/env ruby3.0
_
# After
#!/usr/bin/env ruby
```

* 해결.

(임시 방편이지만 돌아가니까)
