---
title: "[Jekyll] Jekyll Setting"
excerpt: "[7월 7일] Jekyll 시작하기 "
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - Jekyll
  - Study


---
# Jekyll을 이용한 개인 블로그 만들기

### Ruby 설치하기
[Reference](https://gorails.com/setup/ubuntu/16.04) 참고

### Jekyll 설치하기
[Reference](https://jekyllrb-ko.github.io/) 사이트를 참고해 설치 한다.

```bash
 gem install jekyll
```

블로그 페이지를 만들고 *jekyll serve* 을 통해 구동한다.
[http://localhost:4000](http://localhost:4000) 에 접속하여 확인 가능하다.

```bash
 jekyll new [Blog name]
 cd [Blog name]
 jekyll serve
```
### Blog를 Github와 연동하기
1. Github에서 **[UserID].github.io** 이름을 가진  repository를 만들어 준다.
1. Jeykll을 통해 만든 Blog를 위의 repository에 올려준다.

```bash
 cd [Blog name]
 git init
 git add .
 git commit -m "frist commit"
 git remote add origin [HTTPS | SSH]
 git push -u origin master
```

1. Github에 올라간 Blog 코드를 확인하고, 마지막으로 **_config.yml**의 url을 *http://[UserID].github.io* 로 바꿔준다.

#### [Jekyll 공식 사이트](https://jekyllrb-ko.github.io/)에서 다양한 참조 문서를 활용 가능하다.

#### [Jekyll Theme 사이트](http://jekyllthemes.org/)에서 다양한 Jekyll Theme들을 이용할 수 있다.
