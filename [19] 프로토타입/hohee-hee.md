**[19] 프로토타입 (7문항)**

1. 프로토타입 객체는 객체지향 프로그래밍의 특징 중 어떤 특징을 구현하기 위해 사용되나요?

2. 프로토타입의 constructor 프로퍼티는 무엇을 가리키나요?

3. 다음 코드의 출력 결과와 그 이유를 말해주세요.

   ```js
   const person = { name: "Alice" };
   console.log(person.__proto__.constructor === Object);
   ```

4. 프로토타입 체인은 무엇인가요?

5. 프로토타입 체인의 종점의 프로토타입은 무엇이고, 만약 프로토타입체인의 종점에서도 프로퍼티를 검색할 수 없으면 무엇을 반환하나요?

6. 만약 순환참조하는 프로토타입 체인이라면 어떤 일이 발생하나요?

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
