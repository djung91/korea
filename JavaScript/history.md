ECMAScript Version
ECMAScript 3 : ECMA-262 3rd edition (1999.12)
가장 범용적으로 지원되는 버전이다.

ECMAScript 5 : ECMA-262 5th edition (2009.12)
HTML5와 함께 출현한 표준안이다. JSON(JavaScript Object Notation)과 Strict Mode가 추가되었다. IE 9 이상(85%)이나 그 외 브라우저에서만 작동한다.

ECMAScript 6 : ECMA-262 6th edition (2015.06)
let, const 키워드, Arrow Function, class, Symbol 타입 등이 추가되었다.


모던 브라우저의 ES6 지원은 97%로 거의 100%에 육박하지만 IE 지원을 고려한다면 babel과 같은 Transpiler를 사용하여야 한다.

#### body 요소의 가장 아래에 자바스크립트를 위치시키는 것은 좋은 아이디어이다. 그 이유는 아래와 같다.

- HTML 요소들이 스크립트 로딩 지연으로 인해 렌더링에 지장 받는 일이 발생하지 않아 페이지 로딩 시간이 단축된다.

- DOM이 완성되지 않은 상태에서 자바스크립트가 DOM을 조작한다면 에러가 발생한다.
