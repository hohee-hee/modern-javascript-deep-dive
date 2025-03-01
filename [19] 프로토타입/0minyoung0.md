아래 코드의 실행 결과와 왜 그렇게 동작하는지 설명해주세요.
```js
const Person = name => {
  this.name = name;
};

console.log(Person.prototype);
```

아래 코드의 실행 결과와 왜 그렇게 동작하는지 설명해주세요.
```js
const Person = (function () {
  function Person(name) {
    this.name = name;
  }
  Person.prototype.sayHello = function () {
    console.log(`Hi! My name is ${this.name}.`);
  };
  return Person;
})();
const me = new Person("Lee");
me.sayHello = function () {
    console.log(`Hey! My name is ${this.name}.`);
};

me.sayHello();
delete me.sayHello;
me.sayHello();
delete me.sayHello;
me.sayHello();
```

instanceof 연산자에 대해서 설명해주세요.