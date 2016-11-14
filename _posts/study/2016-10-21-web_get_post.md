---
title: "[Web] Get & Post"
excerpt: "[10월 21일] GET & POST 공부"
header:
  teaser: /posts/study.jpg
categories:
  - 3. Study
tags:
  - Web
  - GET
  - POST

---
# GET방식과 POST방식

WEB에서 `GET` 방식과 `POST` 방식은 **HTTP Protocol** 을 이용해 서버에게 무엇인가를 전달하기 위해 사용한다.

## GET
  - `GET` 방식을 데이터를 URL의 ? 뒤에 쌍으로 이어 붙여서 전송한다.
  - URL뒤에 붙여서 전송하기 때문에 길이제한이 있어서 많은 양의 데이터에 부적합하다.
  - `GET` 은 가져온다는 성격이다. 즉 *Select* 적인 성향으로, 서버에서 데이터를 가져와서 보여주는 용도로 주로 사용된다(상태 변경 X).
  - FORM에서 ID와 PASSWORD를 전달할 때 사용한다면 부적절하다. URL에 Password가 노출되기 때문이다.

## POST
  - `POST` 방식을 데이터를 Body 안에 숨겨서 전송한다.
  - 길이제한이 없기 때문에 많은 양의 데이터에 적합하다.(용량 제한은 존재)
  - `POST` 은 무언가를 수행한다는 성격이다. 서버의 값이나 상태를 변경하기 위해 주로 사용된다.

```
 GET과 POST방식을 단순히 보안상의 문제로 생각할 수는 없다. 보안은 조금 더 복잡한 문제이다.
```

```
 예를들어, 서버에 DB값을 삭제하는 것을 GET으로 구현한다면 문제가 생길 수도 있다. 만약 웹페이지의 로드 속도를 높이기 위해 Google의 Accelerator와 같은 BOT이 작동한다면, 모든 URL을 방문하는 과정에서 DB의 값을 지워 버리는 일이 발생할 수 있다.
```

> GET방식과 POST방식을 적절하게 사용할 필요성이 있다.
