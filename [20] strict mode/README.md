# [20] strict mode

### 1. 자바스크립트의 암묵적 전역(implicit global)에 대해 설명해주세요.

- 선언하지 않고 사용한 변수를 자바스크립트 엔진이 전역 객체의 프로퍼티로 동적 생성하는 것.

### 2. strict mode를 적용하는 방법에 대해 설명해주세요.

- 전역의 선두 또는 함수 몸체의 선두에 `'use strict';`를 추가한다.

### 3. strict mode가 발생시키는 에러에는 어떤 것이 있는지 설명해주세요.

- 암묵적 전역 (선언하지 않은 변수를 참조하면 ReferenceError가 발생)
- 변수, 함수, 매개변수의 삭제 (delete 연산자로 변수, 함수, 매개변수를 삭제하면 SyntaxError가 발생)
- 매개변수 이름의 중복 (중복된 매개변수 이름을 사용하면 SyntaxError가 발생)
- with문의 사용 (with문을 사용하면 SyntaxError가 발생)

### 4. strict mode 적용에 의해 발생하는 에러 외에 다르게 동작하는 것에는 어떤 것이 있는지 설명해주세요.

- strict mode에서 함수를 일반 함수로서 호출하면 this에 undefined가 바인딩 됨, 에러는 발생하지 않음
- strict mode에서 매개변수에 전달된 인수를 재할당하여 변경해도 arguments 객체에 반영되지 않음

### 5. 아래 코드의 실행 결과와 이유를 설명해주세요.

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

- 10, ReferenceError
- 선언하지 않은 변수에 값을 할당하면 전역 객체 프로퍼티로 추가되나, strict mode에서는 이를 방지함
