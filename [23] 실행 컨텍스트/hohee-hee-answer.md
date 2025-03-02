**[23] 실행 컨텍스트 (6문항)**

1. 실행 컨텍스트란 무엇인가요?

- 소스코드를 실행하는데 필요한 환경을 제공하고 코드의 실행 결과를 실제로 관리하는 영역

2. 실행 컨텍스트에서 식별자와 스코프, 그리고 코드 실행 순서는 각각 무엇으로 관리하나요?

- 식별자, 스코프 : 렉시컬 환경
- 코드 실행 순서 : 실행 컨텍스트 스택

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

   1. push(전역 실행 컨텍스트)
   2. push(outer 함수 실행 컨텍스트)
   3. push(innerSecond 함수 실행 컨텍스트)
   4. pop(innerSecond 함수 실행 컨텍스트)
   5. push(innerFirst 함수 실행 컨텍스트)
   6. pop(innerFirst 함수 실행 컨텍스트)
   7. pop(outer 함수 실행 컨텍스트)
   8. pop(전역 함수 실행 컨텍스트)

4. 렉시컬 환경의 구성요소로는 무엇이 있고 각각 무엇인지 설명해주세요.

- `EnvironmentRecord` : 스코프에 포함된 식별자를 등록하고 등록된 식별자에 바인딩된 값을 관리하는 저장소
- `OuterLexicalEnvironmentReference` : 외부 렉시컬 환경에 대한 참조 - 상위 스코프

5. 전역 렉시컬 환경의 외부 렉시컬 환경에 대한 참조에는 무엇이 할당되나요?

- null

6. 블록 레벨 스코프에서 새로운 렉시컬 환경은 어떻게 생성되고 관리되나요?

- 선언적 환경 레코드를 갖는 렉시컬 환경을 새롭게 생성하여 기존의 전역 렉시컬 환경을 교체
- 해당 코드 블록의 실행이 종료되면 실행 이전의 렉시컬 환경으로 되돌립니다.
