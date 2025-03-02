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

   nonStrict();
   strict();
   ```

2. strict mode일 때 에러를 발생시키는 사례에는 무엇이 있나요?
