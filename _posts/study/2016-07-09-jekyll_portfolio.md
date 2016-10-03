---
title: "[Jekyll] Portfolio"
excerpt: "[7월 9일] 블로그에 Collection 추가하기 "
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - Jekyll
  - Study


---

# 블로그에 Collection 추가하기

### 블로그의 `_post` 디렉토리와 같이 디렉토리에 게시물을 올려서 관리하는 것을 추가 하였다

첫번째로, `_portfolio` 라는 디렉토리를 만들었 다. 이 폴더에는 **포트폴리오** 게시물을 올려둘 것이다.

```bash
mkdir _portfolio
```
두번째로, `_pages` 디렉토리에 **portfolio** 들을 보여줄 페이지를 만들어야 한다. `_pages` 디렉토리에 `portfolio.html` 파일을 만들었다

```html
---
layout: archive
title: "Portfolio"
permalink: /portfolio/
author_profile: true
---

{% include base_path %}

<div class="grid__wrapper">
  {% for post in site.portfolio %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>
```
> portfolio.html 파일을 보면 site.portfolio 의 포스트들을 모두 가져온다. 그때 archive-single Layout형식, Grid 타입으로 가져온다.

마지막으로, `_config.yml` 파일을 수정해 주어야 한다. portfolio에 대한 collections을 추가해 주어야한다. 또한, default 값도 추가해 주어야 한다.

```yml
collections:
  portfolio:
    output: true
    permalink: /:collection/:path/

defaults:
  # _portfolio
  - scope:
      path: ""
      type: portfolio
    values:
      layout: single
      author_profile: false
      comments: true
      share: true
      ..
      ..
```

이제 블로그의 `Navigation` 을 수정해서 메뉴를 추가해주어야 한다.
**_data/navigation.yml** 에 들어가 메뉴를 추가해준다.

### 이제 `_portfolio` 디렉토리에 `*.md` 파일을 추가하면 `_pages/portfolio` 에 자동으로 추가될 것이다.

### 이렇게 파일디렉토리로 포스트와 포트폴리오를 따로 관리 할 수 있다.
