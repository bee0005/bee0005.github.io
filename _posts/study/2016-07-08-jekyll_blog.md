---
title: "[Jekyll] Blog"
excerpt: "[7월 8일] Jekyll을 이용한 개인 블로그 만들기"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - Jekyll
  - Study


---
# Jekyll을 이용한 개인 블로그 만들기

### Jekyll의 무료 Theme중에 minimal-mistakes를 선택하여 개인 블로그를 만들었다.
[내가 사용한 Theme](https://mmistakes.github.io/minimal-mistakes/)

 Blog의 기본 설정들은 모두 `_config.yml` 에서 이루어 졌다.

 post들은 `_posts` 디렉토리에서 page들은 `_pages` 디렉토리에서 관리 할 수 있어서, 기존의 웹페이지 보다 효율적이고 직관적으로 코드를 작성 할 수 있을 것 같다.

 페이지에 적용시키는 javascritp 코드 작성은 `/assets/js/_main.js` 파일에서 작성 할 수 있다.

`_main.js` 파일을 수정 하고 나서는, 반드시 `npm run bundle:js`를 bash창에 입력 해야 적용이 된다.

### 이제 블로그를 시작하는 단계이지만, 꾸준히 관리하여서 완성도 있는 개인블로그를 만들고 싶다.

[Jeahyun's Blog](https://bee0005.github.io)
