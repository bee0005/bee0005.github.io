---
title: "[Ruby on Rails] Login"
excerpt: "[7월 20일] devise gem 사용하기"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - Ruby On Rails
  - Study


---
# 로그인 구현하기

Ruby On Rails Project에서 로그인을 구현을 연습하려고 한다.

로그인 구현을 위한 대표적인 `devise gem`을 이용할 것이다.

### devise gem

구글에 `devise gem`을 검색한다.

  [Github](https://github.com/plataformatec/devise)
 사이트를 참고 한다.

### 프로젝트에 devise gem 설치하기

*devise gem github* 의 Getting Started를 참조하였다.

1. `gem 'devise'` 을 **Gemfile** 에 추가해준다.
2. Bash창에 **Bundle install** 입력한다.
3. **rails generate devise:install** 입력

3. Bash창에 **rails generate devise MODEL** 을 입력하여 모델을 만들어 준다.
> 이때 MODEL은 다른 이름으로 바꿀 수 있다. 예를들어, 사용자의 정보를 저장할 USER로 바꿀 수 있다.

4. **rake db:migrate** 로 위에 입력한 *MODEL* 이라는 DB를 추가하는 작업이다.
> 참고로, `rake routes`를 입력하면 우리가 만들지는 않았지만, 접근 가능한 경로들을 볼 수 있다. 즉, `devise gem`을 설치하고 추가된 경로들을 확인할 수 있다. 대표적으로 **/users/sign_in**
 은 로그인 창이다.

5. `devise gem`의 기본적인 View의 디자인을 바꾸고 싶다면, **rails generate devise:views** 을 입력하면 View를 확인 할 수 있다.


### 기본 적인 로그인 구현
`devise gem`에 대한 모든 Document는 Github에 자세히 나와있다.

가장 대표적인 명령어가 있다.
- **user_signed_in?** 은 User가 현재 로그인 되어 있는 지를 확인 할 수 있다.
> Controller에 로그인이 안되 있다면, 로그인 페이지로 이동시키는 코드를 만들 수 있다.

```ruby
  unless user_signed_in?
    redirect_to "/users/sign_in"
  end
```
- **current_user** 현재 로그인된 사용자 정보이다.

### 기본적인 로그아웃 구현
- 로그인이 된 후 페이지에서 *로그 아웃* 버튼을 만들고 Link을 */users/sign_out* 으로 지정한다.

```html
<a href="/users/sign_out">로그아웃</a>
```

- **config/initializers/devise.rb** 의 *config.sign_out_via* 의 설정을 바꿔준다.

> config.sign_out_via = :delete 변경 전
  config.sign_out_via = :get 변경 후
