# [19] 프로토타입

### 1.프로토타입 객체는 객체지향 프로그래밍의 특징 중 어떤 특징을 구현하기 위해 사용되나요?

- 상속

### 2. 프로토타입의 constructor 프로퍼티는 무엇을 가리키나요?

- 자신을 참조하고 있는 생성자함수

### 3. 다음 코드의 출력 결과와 그 이유를 말해주세요.

```js
const person = { name: "Alice" };
console.log(person.__proto__.constructor === Object);
```

- true / 리터럴표기법으로 생성된 객체는 Object의 프로토타입을 상속받기 때문에 constructor도 Object를 가리킨다

### 4. 프로토타입 체인은 무엇인가요?

- 프로토타입 체인은 객체가 자신의 프로퍼티를 찾을 때, 상위객체인 프로토타입에서 그 프로퍼티를 찾는 메커니즘
- 상속과 프로퍼티 검색을 위한 메커니즘

### 5. 프로토타입 체인의 종점의 프로토타입은 무엇이고, 만약 프로토타입체인의 종점에서도 프로퍼티를 검색할 수 없으면 무엇을 반환하나요?

- null, undefined

### 6. 만약 순환참조하는 프로토타입 체인이라면 어떤 일이 발생하나요?

- 종점이없기 때문에 검색 시 무한루프에 빠진다 (실제로는 TypeError 발생)

### 7. 다음 코드의 실행 결과와 이유를 설명해주세요.

```js
const Person = (function () {
  function Person(name) {
    this.name = name;
  }

  return Person;
})();

const me = new Person("Kwon");
const you = new Person("Jeong");

const goodbye = {};

Object.setPrototypeOf(me, goodbye);

console.log(me instanceof Person);
console.log(me instanceof Object);

console.log(you instanceof Person);
console.log(you instanceof Object);
```

- false, true, true, true / me는 새로운 프로토타입이 할당되면서 프로토타입 체인에 Person 객체가 사라지게 됨

### 8. 아래 코드의 실행 결과와 왜 그렇게 동작하는지 설명해주세요.

```js
const Person = (name) => {
  this.name = name;
};

console.log(Person.prototype);
```

- undefined, 생성자 함수로서 호출할 수 없는 함수, 즉 non-constructor는 프로토타입이 생성되지 않는다.

### 9. 아래 코드의 실행 결과와 왜 그렇게 동작하는지 설명해주세요.

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

- Hey! My name is Lee.
- Hi! My name is Lee.
- Hi! My name is Lee.
- 인스턴스 메서드 sayHello가 동명의 프로토타입 메서드를 오버라이딩(overriding)했고 프로토타입 메서드는 가려진다. 이와 같이 상속 관계에 의해 프로퍼티가 가려지는 현상을 프로퍼티 섀도잉(property shadowing)이라고 한다.
- 또한 하위 객체에 의해 프로토타입의 프로퍼티를 변경하거나 삭제할 수는 없으므로, 두번째 delete me.sayHello 구문의 실행은 아무 의미를 가지지 않는다. 프로토타입 프로퍼티를 변경 또는 삭제하려면 프로토타입에 직접 접근해야 한다. (ex. delete Person.prototype.sayHello)

### 10. instanceof 연산자에 대해서 설명해주세요.

- instanceof 연산자는 이항 연산자로, 좌변에 객체를 가리키는 식별자, 우변에 생성자 함수를 가리키는 식별자를 피연산자로 받는다. 우변의 생성자 함수의 prototype에 바인딩 된 객체가 좌변의 객체의 프로토타입 체인상에 존재하면 true로, 아니면 false로 평가된다.
