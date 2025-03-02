**[23] 실행 컨텍스트 (6문항)**

1. 실행 컨텍스트란 무엇인가요?

2. 실행 컨텍스트에서 식별자와 스코프, 그리고 코드 실행 순서는 각각 무엇으로 관리하나요?

3. 아래 소스코드를 실행할 때, 실행 컨텍스트 스택은 어떻게 변화하나요?

   ```js
   const x = 1;
   function outer(a) {
     const y = 100;

     function innerFirst(b) {
       console.log(`first is ${b}`);
     }

     function innerSecond(c) {
       console.log(`second is ${c}`);
     }

     innerSecond("telephone");
     innerFirst("paparazzi");

     return a + y;
   }

   outer(10);
   ```

4. 렉시컬 환경의 구성요소로는 무엇이 있고 각각 무엇인지 설명해주세요.

5. 전역 렉시컬 환경의 외부 렉시컬 환경에 대한 참조에는 무엇이 할당되나요?

6. 블록 레벨 스코프에서 새로운 렉시컬 환경은 어떻게 생성되고 관리되나요?
