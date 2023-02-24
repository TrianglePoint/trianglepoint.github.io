---
layout: post
title:  "jekyll 로컬 serve 문제 해결"
date:   2023-02-24 15:06:00 +0900
categories: Linux
---
블로그 글 작성을 Ubuntu에서 하려고 ruby, jekyll 등을 새로 설치, 로컬에서 블로그를 테스트하려는데 에러가 발생.<br />
(아마도 오랜만에 설치하면서 버전들이 업데이트된 것 같다, 아래 문제들은 그에 대한 대응을 하지 않아서 발생한 것)<br />

Ruby 3.0~ 을 사용중인데 이로 인해 발생한 듯한 webrick 관련 에러는 `gemfile에 추가`한 것으로 해결.<br />

gem의 pathutil.rb 에서 파일 읽기가 실패. `gemfile.lock을 삭제`하고 새로 bundle install해주니 해결.<br />
이런 의존성 문제는 기본적인 문제라 다들 알고 있겠지만 나는 몰랐다...<br />

글로 적어두었으니 이후에도 문제없겠지.