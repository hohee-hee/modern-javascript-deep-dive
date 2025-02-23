1. 프로토타입 객체는 객체지향 프로그래밍의 특징 중 어떤 특징을 구현하기 위해 사용되나요?

- 상속

2. 프로토타입의 constructor 프로퍼티는 무엇을 가리키나요?

- 자신을 참조하고 있는 생성자함수

3. 다음 코드의 출력 결과와 그 이유를 말해주세요.

```js
const person = { name: "Alice" };
console.log(person.__proto__.constructor === Object);
```

- true / 리터럴표기법으로 생성된 객체는 Object의 프로토타입을 상속받기 때문에 constructor도 Object를 가리킨다

4. 프로토타입 체인은 무엇인가요?

- 프로토타입 체인은 객체가 자신의 프로퍼티를 찾을 때, 상위객체인 프로토타입에서 그 프로퍼티를 찾는 메커니즘
- 상속과 프로퍼티 검색을 위한 메커니즘

5. 프로토타입 체인의 종점의 프로토타입은 무엇이고, 만약 프로토타입체인의 종점에서도 프로퍼티를 검색할 수 없으면 무엇을 반환하나요?

- null, undefined

6. 만약 순환참조하는 프로토타입 체인이라면 어떤 일이 발생하나요?

- 종점이없기 때문에 검색 시 무한루프에 빠진다

7. 다음 코드의 실행 결과와 이유를 설명해주세요.

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

- FTTT / me는 새로운 프로토타입이 할당되면서 프로토타입 체인에 Person 객체가 사라지게 됨
