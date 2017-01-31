### Node.js 전역 변수, 객체
 - node.js에는 `window` 객체를 가지고 있지 않다.
 > window 객체는 웹브라우저에서 동작하는 자바스크립트의 최상위 객체이다. 웹브라우저 자체와 관련된 속성과 메소드를 가지고 있다.

 - 대신 **전역 변수** 와 **전역 함수** 를 가지고 있습니다.

 1. node.js 전역 변수
  1. *__filename* : 현재 실행 중인 코드의 파일 경로
  2. *__dirname* : 현재 실행 중인 코드의 폴더 경로

 2. node.js 전역 객체
  1. *console* : 콘솔 화면과 관련된 기능을 다루는 객체
  2. *exports* : 모듈과 관련된 기능을 다루는 객체
      - 모듈은 기능을 쉽게 사용하고자 메서드와 속성을 미리 정의해 모아 놓은 것이다.
  3. *process* : 프로그램과 관련된 기능을 다루는 객체
      - 웹 브라우저에서 동작하나 JS가 가지고 있지 않는 node.js만의 객체이다.

> 그 밖에 자바스크립트가 가지고 있는 String, Number, Math 객체 등도 전역 객체로 가지고 있다.

---
#### 모듈 사용하기
 - 모듈을 생성할 때는 **exports** 객체를 사용한다.

`main.js` 에서 `testModule.js` 모듈을 불러와 사용하는 예이다.

```JavaScript
//testModuel.js
exports.fnc1 = function(){
  console.log("testModule의 fnc1 입니다.");
}

exports.fnc2 = function(){
  console.log("testModule의 fnc2 입니다.");
}
```

```JavaScript
//main.js

//모듈을 추출한다
var module = require('./testModule.js');
//모듈 사용
module.fnc1();  //testModule의 fnc1 입니다.
module.fnc2();  //testModule의 fnc2 입니다.
```

모듈을 생성할 때는 **exports** 객체를 사용하고 모듈을 추출할 때는 **require()** 객체를 사용한다.
