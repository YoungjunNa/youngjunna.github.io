---
layout: post
title: "R$ Docker로 올린 R Studio에서 유저를 추가하는 방법"
date: 2019-10-01
comments: true
author: Youngjun Na
categories:
  - R
---

Docker를 이용해서 R Studio Server를 올린 이후 새로운 유저를 추가하는 방법은 다음과 같습니다.

1. `docker exec -it your_name bash`를 이용해 rstudio server가 설치된 이미지로 들어갑니다.  
2. `adduser your_user_name` 명령어를 이용해 유저를 추가합니다.

이렇게 할 경우 sudo 유저가 아니면 패키지를 설치 할 수 없는 이슈가 발생할 수 있습니다. 다음과같은 에러메시지와 함께 말이죠.

> ERROR: no permission to install to directory ‘/usr/local/lib/R/site-library’

그럴 경우 `sudo usermod -a -G staff your_user_name`을 이용해 Staff로 등록을 하면 정상적으로 패키지의 설치가 가능해집니다.  