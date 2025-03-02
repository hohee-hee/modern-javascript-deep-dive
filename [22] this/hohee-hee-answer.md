**[22] this (6문항)**

1. `this`란 무엇인가요?

- 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기참조변수
- 자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조할 수 있음

2. strict mode가 적용 되었을 때와 아닐 때, 아래 코드를 브라우저에서 실행시킬 때의 결과는 무엇인가요?

   ```js
   function foo() {
     console.dir(this);
   }

   foo();
   ```

- strict mode: undefined
- non-strict mode : Window

3. 다음 코드를 브라우저 환경에서 실행시켰을 때의 결과를 설명해주세요.

   ```js
   var value = 1;

   const obj = {
     value: 100,
     normalCallback() {
       setTimeout(function () {
         console.log(this.value);
       }, 100);
     },
     arrowCallback() {
       setTimeout(() => console.log(this.value), 100);
     },
   };

   obj.normalCallback(); // 1
   obj.arrowCallback(); // 100
   ```

4. 메서드 내부의 this와 생성자 함수 내부의 this에는 각각 무엇이 바인딩 되나요?

- 메서드 내부의 this : 메서드를 호출한 객체
- 생성자 함수 내부의 this : 생성자 함수가 생성할 인스턴스

5. `Function.prototype.call`과 `Function.prototype.bind`의 차이는 무엇인가요?

- `call`: 함수를 호출
- `bind` : 함수를 호출하지 않음 : 첫 번째 인수로 전달한 값으로 this 바인딩이 교체된 함수를 새롭게 생성해 반환환

6. 다른 언어(C++, 자바 등)의 `this`와 자바스크립트의 `this`의 차이점은 무엇인가요?

- 다른 언어 : 언제나 클래스가 생성하는 인스턴스를 가리침
- JS : 바인딩이 동적으로 결정정
