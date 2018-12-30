모든 언어가 갖고 있는 기본적인 개념

JavaScript 에서는 Scope는 2가지 종류

> Global Scope 
> Local Scope

##### JavaScrpt는 다른 언와 다른 Scope 특징을 갖는다

대부분의 언어는 *block-level scope*를 사용하지만, 
(code block 개념 { ... } )

Javascript는 *Funtion-level scope*를 사용한다

![sample](https://images2.imgbox.com/33/85/weeXyXDk_o.jpg)

1. Globla Scope
Global object 인 window의 property 이기도 하다

2. Non block-level Scope  
`if(trur) {
	var major = "Math";
}`
`console.log(major); //Math 출력`

var 키워드를 사용하지 않고 지역변수의 이름을 전역변수와 같이 사용하면, 
전역 변수에 접근하여 값을 변경할 수 있다.

