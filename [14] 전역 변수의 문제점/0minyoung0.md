다음 코드의 실행 결과가 무엇일까요?
```js
var x = 'global';
function foo() {
    console.log(x);
    var x = 'local';
}

foo();
console.log(x);
```

전역 변수의 문제점에는 어떤 것이 있는지 설명해주세요.

다음 코드의 실행 결과가 무엇일까요?
```js
var Counter = (function () {
    var num = 0;

    return {
        increase() {
            return ++num;
        },
        decrease() {
            return --num;
        }
    };
}());

console.log(Counter.num);
console.log(Counter.increase());
console.log(Counter.increase());
console.log(Counter.decrease());
console.log(Counter.decrease());
```