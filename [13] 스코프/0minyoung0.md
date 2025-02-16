스코프가 무엇인지 설명해주세요.

자바스크립트에서 함수 레벨 스코프(function level scope)와 블록 레벨 스코프(block level scope)에 대해서 설명해주세요.

아래 코드의 실행 결과가 무엇인지, 왜 그런지 설명해주세요.
```js
var x = 1;
function foo() {
    var x = 10;
    bar();
}
function var() {
    console.log(x);
}

foo();
bar();
```