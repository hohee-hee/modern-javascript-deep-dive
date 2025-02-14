함수의 매개변수(parameter)와 인수(argument)의 차이를 설명해주세요.

함수를 적절히 사용했을 때 어떤 이점을 가지는지 설명해주세요.

함수 선언문은 표현식이 아닌 문이므로 변수에 할당할 수 없습니다. 그러나 아래와 같은 코드가 동작하는 이유를 설명해주세요.
```js
var add = function add(x, y) {
    return x + y;
};

console.log(add(2, 5)); // 7
```

자바스크립트의 함수는 객체지만 일반 객체와는 다릅니다. 어떤 특징이 있는지 설명해주세요.

아래 코드의 실행 결과는 무엇이고, 그 이유가 무엇인지 설명해주세요.
```js
function add(x, y) {
    return x + y;
}

console.log(add(2));
```

콜백 함수(callback function)와 고차 함수(Higher-Order Function, HOF)에 대해서 설명해주세요.

순수 함수(pure function)와 함수형 프로그래밍에 대해서 설명해주세요.