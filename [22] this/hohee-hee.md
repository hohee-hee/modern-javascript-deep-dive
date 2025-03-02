**[22] this (6문항)**

1. `this`란 무엇인가요?

2. strict mode가 적용 되었을 때와 아닐 때, 아래 코드를 브라우저에서 실행시킬 때의 결과는 무엇인가요?

   ```js
   function foo() {
     console.dir(this);
   }

   foo();
   ```

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

   obj.normalCallback();
   obj.arrowCallback();
   ```

4. 메서드 내부의 this와 생성자 함수 내부의 this에는 각각 무엇이 바인딩 되나요?

5. `Function.prototype.call`과 `Function.prototype.bind`의 차이는 무엇인가요?

6. 다른 언어(C++, 자바 등)의 `this`와 자바스크립트의 `this`의 차이점은 무엇인가요?
