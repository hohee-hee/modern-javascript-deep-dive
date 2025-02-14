객체는 프로퍼티와 메서드로 구성된 집합체입니다. 프로퍼티와 메서드가 무엇인지 설명해주세요.

아래 코드의 실행 결과는 무엇일까요?
```js
var foo = {
    name: 'Lee',
    name: 'Kim'
};

console.log(foo);
```

아래 코드를 실행하면 어떻게 될까요?
```js
var person = {
    name: 'Lee'
};

console.log(person.age);
```

아래 코드를 실행하면 어떻게 될까요?
```js
var person = {
    name: 'Lee'
};
person.age = 20;
delete person.age;
delete person.address;

console.log(person);
```