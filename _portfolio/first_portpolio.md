---
title: "Google Calendar Bot"
excerpt: "Facebook Messenger Bot입니다. Bot을 이용해 구글 캘린더를 관리할 수 있습니다."
header:
  image: foo-bar-identity.jpg
  teaser: bio-photo.jpg
sidebar:
  - title: "Role"
    image: bio-photo.jpg
    image_alt: "logo"
    text: "Developer"
  - title: "Member"
    text: "2명"
  - title: "Term"
    text: "2주"
gallery:
  - url: unsplash-gallery-image-1.jpg
    image_path: unsplash-gallery-image-1-th.jpg
    alt: "placeholder image 1"
  - url: unsplash-gallery-image-2.jpg
    image_path: unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
  - url: unsplash-gallery-image-3.jpg
    image_path: unsplash-gallery-image-3-th.jpg
    alt: "placeholder image 3"
---

## Facebook Bot

2016년 4월 12일 [Facebook Developer Conference F8](https://www.fbf8.com/)에서 Messenger Flatform Bot을 발표했다.

메신저 플랫폼인 Bot의 전망과 미래, 그리고 Bot의 가능성에 대해 설명하였다.

Messenger Flatform인 Bot의 가장 큰 특징은 해당 기능의 APP을 설치 하지 않고도, Facebook Messenger를 통해 다양한 Bot들을 이용할 수 있다는 것이다.

Project을 시작하게 된 계기는 Facebook Messenger 플렛폼을 이용한 Bot을 만들어 보고 싶었다.


## Bot의 기능

2016년 5월부터 본격적으로 프로젝트를 시작하였다.

Google Calendar을 Bot과 접목시켜, Bot을 이용해 구글 캘린더를 관리하는 것을 주요 기능으로 개발을 시작하였다.

Google Calendar API을 이용하여 Bot을 통해 구글 캘린더를 관리 할 수 있었다.

Node.js 라는 언어를 처음 접해보았지만, Javascript와 매우 비슷하여 어렵지 않게 시작 할 수 있었다.

또한, Node.js 와 많이 사용되는 Mongo DB를 이용했으나, Google API을 이용 했기 때문에 사용자에 대한 인증 정보만 저장할 뿐 특별한 DB 사용은 없었다.

그리고

## Wit.ai

F8에서 `Wit.ai`에 대한 소개가 있었다. `wit.ai` API을 통해 Bot에 AI를 이용할 수 있다는 내용이었다.

알파고에 대한 관심과 이슈로 나 또한 AI에 대한 관심이 많았다. 그래서 우리는 생소하지만 `wit.ai` API을 사용해 보기로 결정하였다.

개인적인 의견으로는 AI에 대한 큰 기대가 있었는 지는 모르겠지만, 솔직히 많이 실망스러웠다.

Training을 해도 오류가 많았고, 우리가 원하는 문맥을 정확하 파악하는 것에 어려움이 있었다.

그래도 구글 캘린더에 일정을 추가하거나 삭제, 수정하는 단어들은 잘 인지하였다.

> 예를들어, 추가를 의미하는 add, insert, plus, register .. 
> 삭제를 의미하는 delete, remove ..

하지만, 날짜를 입력하거나 기간을 이상하게 입력하는 다양한 가능성에 대한 처리가 부족한듯 싶었다.

그래도, `Today`, `Tomorrow` 와 같은 Keyword를 따로 입력하지 않아도 날짜로 인지하는 AI가 신기하였다.

다음에는 `wit.ai`를 조금 더 공부하여서 Bot에 완성도를 높이고 싶다.

## Demo
데모 비디오

{% include gallery caption="This is a sample gallery to go along with this case study." %}

## 개발 환경
- Node.js
- wit.ai
- Mongo DB
- C9 / Heroku


