# [07] 연산자

### 1. 산술 연산자를 사용한 연산이 불가능한 경우에 반환하는 값이 무엇일까요?

- `NaN`

### 2. `+` 연산자가 문자열 연결 연산자와 산술 연산자로 동작하는 조건에 대해 설명해주세요.

- 피연산자 중 하나라도 문자열이면 문자열 연결 연산자로 동작
- 그 외는 산술 연산자로 동작

### 3. `1 + false` 연산이 수행될 때 발생하는 과정에 대해 설명해주세요.

- `false`가 0으로 변환되어서 `1 + false`는 1이 된다.

### 4. `-0 === +0`, `Object.is(-0, +0)`의 실행 결과와 `NaN === NaN`, `Object.is(NaN, NaN)`의 실행 결과는 무엇인가요?

- `-0 === +0` : true
- `Object.is(-0, +0)` : false
- `NaN === NaN` : false
- `Object.is(NaN, NaN)` : true

### 5. 자바스크립트에서 `==(동등비교)`와 `===(일치비교)`는 어떤 차이가 있나요?

- `==`는 값만을 비교하고 `===`은 타입비교도 같이 한다.

### 6. `var1`, `var2`, `var3`은 각각 어떤 값이 나올까요?

```js
const var1 = 1 + NaN; // NaN
const var2 = 1 + null; // 1
const var3 = 1 + undefined; // NaN
```

- `undefined`는 숫자로 변환되지 않는다.

### 7. `typeOfNull`과 `typeOfNoDeclare`의 값은 무엇인가요?

```js
const typeOfNull = typeof null; // object
const typeOfNoDeclare = typeof value; // undefined
```

### 8. if 문과 삼항 연산자는 동일한 역할을 할 수 있어요. 하지만 둘의 차이는 무엇인가요?

- if 문 : 표현식이 아니고, false인 경우에 대한 처리를 필수적으로 할 필요가 없다.
- 삼항연산자 : 삼항 조건 연산자는 값으로 평가될 수 있는 표현식이며 false인 경우도 처리해주어야한다.
