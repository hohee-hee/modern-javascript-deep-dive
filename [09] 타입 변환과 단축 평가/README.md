# [09] 타입 변환과 단축 평가

### 1.`false`값으로 평가되는 값에는 무엇이 있나요?

- `false`, `undefined`, `null`, 0, -0, `NaN`, `''`

### 2. 명시적 타입 변환 하는 방법에는 방법에는 무엇이 있나요?

- 표준 빌트인 생성자 함수 호출
- 빌트인 메서드를 사용하는 방법
- 암묵적 타입변환 (ex. `+` 단항 연산자를 이용하는 방법 등등)

### 3. 다음 코드의 실행 결과는 무엇인가요?

```js
const type = "Cat";
const isDog = false;

console.log(type || isDog); // 'Cat'
console.log(isDog || type); // 'Cat'
console.log(isDog && type); // false
console.log(type && isDog); // false
```

### 4. 빈 문자열, 빈 배열, 빈 객체가 각각 Truthy인지 Falsy인지 설명해주세요.

- 빈 문자열 : Falsy
- 빈 배열 : Truthy
- 빈 객체 : Truthy

### 5. 옵셔널 체이닝 연산자에 대해서 설명해주세요.

- `?.`는 좌항의 피연산자가 `null` 또는 `undefined`인 경우 `undefined`를 변환하고 그렇지 않으면 우항의 프로퍼티 참조를 이어간다.

### 6. null 병합 연산자에 대해서 설명해주세요.

- `??`는 좌항의 피연산자가 `null` 또는 `undefined`인 경우 우항의 피연산자를 반환하고, 그렇지 않으면면 좌항의 피연산자를 반환한다.
