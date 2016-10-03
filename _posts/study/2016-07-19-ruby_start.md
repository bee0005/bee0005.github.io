---
title: "[Ruby on Rails] Setting"
excerpt: "[7월 19일] Ruby on Rails 설치 "
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - Ruby On Rails
  - Study


---
# Ruby On Rails 설치

### Ubuntu 16.04 버전에 설치

  [Reference](https://gorails.com/setup/ubuntu/16.04)
 사이트를 참고해 설치 하였습니다.

# Ruby On Rails 프로젝트 만들기

### 프로젝트 만들기
터미널을 이용해 프로젝트를 만들어 준다.  
Project Directory에서  Controller를 만들어 준다.

```bash
rails new [Project Name]
cd [Project Name]
rails g controller home index
```

### 프로젝트 확인하기
프로젝트가 정상적으로 생성 되었는지 확인다.

```bash
rails s
```

프로젝트를 서버에 Run 시키는 명령어이다.

이후 `localhost:3000` 을 WEB에 입력하면 내가 만든 프로젝트에 접근할 수 있다.
