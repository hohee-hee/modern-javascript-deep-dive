원시 타입은 변경 불가능한 값(immutable value)입니다. 불변성(immutability)이 무엇인지 변수에 값이 재할당되는 과정과 함께 설명해주세요.

자바스크립트의 문자열은 어떤 객체인지 설명해주세요.

아래 코드의 실행 결과는 무엇일까요?
```js
var person1 = {
    name: 'Lee'
};
var person2 = {
    name: 'Lee'
};

console.log(person1 === person2);
console.log(person1.name === person2.name);
```