---
title: "Google Calendar Bot"
excerpt: "Facebook Messenger Bot입니다. Bot을 이용해 구글 캘린더를 관리할 수 있습니다."
header:
  image: null
  teaser: /portfolios/bot/1.png
sidebar:
  - title: "Role"
    image: /portfolios/bot/3.png
    image_alt: "logo"
    text: "Developer"
  - title: "Member"
    text: "2명"
  - title: "Term"
    text: "2016.05~ / 2주"
witgallery:
  - url: /portfolios/bot/2.png
    image_path: /portfolios/bot/2.png
    alt: "wit.ai"
fbgallery:
  - url: /portfolios/bot/1.png
    image_path: /portfolios/bot/1.png
    alt: "facebook page"
augallery:
  - url: /portfolios/bot/4.jpg
    image_path: /portfolios/bot/4.jpg
    alt: "인증1"
  - url: /portfolios/bot/5.jpg
    image_path: /portfolios/bot/5.jpg
    alt: "인증2"
  - url: /portfolios/bot/6.jpg
    image_path: /portfolios/bot/6.jpg
    alt: "인증3"
fugallery:
  - url: /portfolios/bot/7.jpg
    image_path: /portfolios/bot/7.jpg
    alt: "인증1"
  - url: /portfolios/bot/8.jpg
    image_path: /portfolios/bot/8.jpg
    alt: "인증2"
  - url: /portfolios/bot/9.jpg
    image_path: /portfolios/bot/9.jpg
    alt: "인증3"
---

## Facebook Bot

2016년 4월 12일 [Facebook Developer Conference F8](https://www.fbf8.com/)에서 Messenger Flatform Bot을 발표했다.

메신저 플랫폼인 Bot의 전망과 미래, 그리고 Bot의 가능성에 대해 설명하였다.

Messenger Flatform인 Bot의 가장 큰 특징은 해당 기능의 APP을 설치 하지 않고도, Facebook Messenger를 통해 다양한 Bot들을 이용할 수 있다는 것이다.

Project을 시작하게 된 계기는 Facebook Messenger 플렛폼을 이용한 Bot을 만들어 보고 싶었다.


## About Project

Google Calendar을 Bot과 접목시켜, Bot을 이용해 구글 캘린더를 관리하는 것을 주요 기능으로 개발을 시작하였다.

Facebook Messenger을 통해 쉽게 일정을 확인하고 간단히 추가, 삭제하고 싶은 기능의 BOT을 만들고 싶었다.

Google Calendar API을 이용하여 Facebook Messenger을 통해 일정을 관리 할 수 있도록 개발하였다.

서버를 따로 없기 때문에 C9을 이용해 개발을 하였다.

특히 Bot 개발을 위해 Node.js 라는 언어를 처음 접해보았지만 공부하였다. Javascript와 매우 비슷하여 어렵지 않게 공부 할 수 있었따.

Node.js 와 많이 사용되는 Mongo DB를 이용했으나, Google API을 이용 했기 때문에 DB에 큰 필요성은 없었다.

하지만, 사용자에 대한 인증 정보를 저장하기 위해 Mongo DB를 사용하였다.

{% include gallery id="fbgallery" caption="facebook page" %}

## Bot의 기능

우리가 프로젝트를 통해 만든 BOT의 대표적인 기능은 3가지이다.

Facebook Messenger을 이용해 Google Calendar에 일정 추가, 조회, 삭제의 기능을 제공하였다.

`wit.ai`가 한글을 제공하지 않아 영어로 입력해야 Bot이 작동한다.

DB에 저장되어 있지 않은 사용자, 즉 처음 이용하는 사용자는 구글 계정 인증을 받아야 한다.


{% include gallery id="augallery" caption="Google calendar 이용을 위한 인증" %}

1. 일정 보기
 Messenger에 **show, display ..** 등과 같이 보기를 의미하는 단어와 날짜를 입력하면 Google Calendar에 등록된 일정을 보여준다.
2. 일정 추가
 Messenger에 **add, insert, register ..** 등과 같이 추가를 의미하는 단어와 날짜를 입력하면 Google Calendar에 일정이 등록된다.
3. 일정 삭제
 Messenger에 **delete, remove ..** 등과 같이 삭제를 의미하는 단어와 일정 제목을 입력하면, 일정 제목의 모든 스케쥴을 가져온다.
 그리고 Messenger 버튼 UI을 통해 원하는 날짜를 선택하여 삭제를 할 수있다.
4. 일정 검색
 Messenger에 **find, search** 와 원하는 keyword를 입력하면 해당 키워드의 모든 일정을 보여준다.


{% include gallery id="fugallery" caption="facebook page" %}

## Wit.ai


F8에서 `Wit.ai`에 대한 소개가 있었다. `wit.ai` API을 통해 Bot에 AI를 이용할 수 있다는 내용이었다.

알파고에 대한 관심과 이슈로 나 또한 AI에 대한 관심이 많았다. 그래서 우리는 생소하지만 `wit.ai` API을 사용해 보기로 결정하였다.

개인적인 의견으로는 AI에 대한 큰 기대가 있었는 지는 모르겠지만, 솔직히 많이 실망스러웠다.

Training을 해도 오류가 많았고, 우리가 원하는 문맥을 정확하 파악하는 것에 어려움이 있었다.

그래도 구글 캘린더에 일정을 추가하거나 삭제, 검색하는 단어들은 잘 인지하였다.

{% include gallery id="witgallery" caption="프로젝트에 이용한 wit.ai 페이지이다." %}
> 예를들어, 추가를 의미하는 add, insert, plus, register .. 

> 삭제를 의미하는 delete, remove ..

> 일정보기를 의미하는 show, display ..

> 검색를 의미하는 find, search ..

하지만, 날짜를 입력하거나 기간을 이상하게 입력하는 다양한 가능성에 대한 처리가 부족한듯 싶었다.

그래도, `Today`, `Tomorrow` 와 같은 Keyword를 따로 입력하지 않아도 날짜로 인지하는 AI가 신기하였다.

다음에는 `wit.ai`를 조금 더 공부하여서 Bot에 완성도를 높이고 싶다.

## Demo
데모 비디오

## 개발 환경
- Node.js
- wit.ai
- Mongo DB
- C9 / Heroku


