---
title: "[Ruby on Rails] Fileupload"
excerpt: "[8월 15일] `CarrierWave gem`"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - Ruby On Rails
  - Study


---
# 간단한 파일 전송

Ruby On Rails Project에서 파일 전송을 구현하고 연습하려고 한다.

파일 전송을 위해 `CarrierWave gem`을 이용할 것이다.

### CarrierWave gem

구글에 `carrierwave gem`을 검색한다.

  [Github](https://github.com/carrierwaveuploader/carrierwave)
 사이트를 참고 한다.

### 프로젝트에 carrierwave gem 설치하기

*devise gem github* 의 Getting Started를 참조하였다.

1. `gem 'carrierwave'` 을 **Gemfile** 에 추가해준다.
2. Bash창에 **Bundle install** 입력한다.
3. **rails generate uploader Avatar** 입력
> 이때 Avatar 다른 이름으로 바꿀 수 있다.

4. *app/uploaders/avatar_uploader.rb* 에 만든 uploader를 커스터마이징 할 수 있다.

### 기본 적인 파일 전송 구현
`carrierwave gem`에 대한 모든 Document는 Github에 자세히 나와있다.

 *app/uploaders/avatar_uploader.rb* 에서  **store_dir** 설정을 통해 파일의 저장 위치를 지정해 줄 수 있다.

```ruby
  uploader = AvatarUploader.new  
  file = params[:file]
  uploader.store!(file)
```

