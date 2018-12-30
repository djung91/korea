클로저는 자바스크립트 고유의 개념이 아니라 함수를 일급 객체로 취급하는 함수형 프로그래밍 언어(Functional Programming language:)에서 사용되는 중요한 특성이다.

클로저는 자바스크립트 고유의 개념이 아니므로 ECMAScript 명세에 클로저의 정의가 등장하지 않는다

함수를 객체처럼 다룬다 - 함수형 프로그래밍

함수를 값으로 다룰수 있는것 (함수 스스로 객체)

함수를 변수에 담아 함수 호출

var f1 = function(a){return a*a;};
console.log(f1); // 함수의 내용이 나옴, 즉 변수f1에 함수가 담겼다
var f2 = add; //add라는 메서드가 있을 때
console.log(f2);

***
> 
> function outerFunc() {
>   var x = 10;
>   var innerFunc = function () { console.log(x); };
>   innerFunc();
> }
> 
> outerFunc(); // 10

함수 outerFunc 내에서 내부함수 innerFunc가 선언되고 호출되었다. 
이때 내부함수 innerFunc는 자신을 포함하고 있는 외부함수 outerFunc의 변수 x에 접근할 수 있다. 
이는 함수 innerFunc가 함수 outerFunc의 내부에 선언되었기 때문이다.


##### 스코프는 함수를 호출할 때가 아니라 *함수를 어디에 선언*하였는지에 따라 결정된다. 이를 렉시컬 스코핑(Lexical scoping)라 한다

> function outerFunc() {
>   var x = 10;
>   var innerFunc = function () { console.log(x); };
>   return innerFunc;
> }
>  *  함수 outerFunc를 호출하면 내부 함수 innerFunc가 반환된다.
>  *  그리고 함수 outerFunc의 실행 컨텍스트는 소멸한다.
>  
> var inner = outerFunc();
> inner(); // 10


함수 outerFunc는 내부함수 innerFunc를 반환하고 생을 마감했다. 
즉, 함수 outerFunc는 실행된 이후 콜스택(실행 컨텍스트 스택)에서 제거되었으므로 함수 outerFunc의 변수 x 또한 더이상 유효하지 않게 되어 변수 x에 접근할 수 있는 방법은 달리 없어 보인다. 그러나 위 코드의 실행 결과는 변수 x의 값인 10이다. 
이미 life-cycle이 종료되어 실행 컨텍스트 스택에서 제거된 함수 outerFunc의 지역변수 x가 다시 부활이라도 한 듯이 동작하고 있다. 뭔가 특별한 일이 일어나고 있는 것 같다.

#### 이처럼 자신을 포함하고 있는 외부함수보다* 내부함수가 더 오래 유지되는 경우*, 외부 함수 밖에서 내부함수가 호출되더라도 외부함수의 지역 변수에 접근할 수 있는데 이러한 함수를 클로저(Closure)라고 부른다.


### 클로저의 활용

1. 상태유지
2. 전역변수의 사용억제
3. 정보의 은닉

[출처] https://poiemaweb.com/js-closure
