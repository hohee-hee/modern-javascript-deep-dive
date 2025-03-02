**[20] strict mode (2문항)**

1. 아래 코드의 실행 결과와 이유를 설명해주세요.

   ```js
   function strict() {
     "use strict";

     x = 10;
     console.log(x);
   }

   function nonStrict() {
     y = 10;
     console.log(y);
   }

   nonStrict(); // 10
   strict(); // ReferenceError
   ```

   `strict` 함수 내부의 `"use strict";`로 인해 strict mode가 적용되어 선언하지 않은 변수를 참조하고 있는 `x = 10;`에서 `ReferenceError`가 발생했다.

2. strict mode일 때 에러를 발생시키는 사례에는 무엇이 있나요?

   - 암묵적 전역 변수 선언 : `ReferenceError`
   - `delete` 연산자로 변수, 함수, 매개변수 삭제 : `SyntaxError`
   - 매개변수 이름의 중복 : `SyntaxError`
   - `with`문의 사용 : `SyntaxError`
