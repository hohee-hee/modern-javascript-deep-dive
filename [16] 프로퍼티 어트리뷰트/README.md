# [16] 프로퍼티 어트리뷰트

### 1. 데이터 프로퍼티와 접근자 프로퍼티의 차이는 무엇인가요?

- 데이터 프로퍼티 : 키와 값으로 구성 / 어트리뷰트 차이 - [[Value]] / [[Writable]]
- 접근자 프로퍼티 : 접근자 함수로 구성 / 어트리뷰트 - [[Get]] / [[Set]]

### 2. 아래 코드의 실행 결과는 무엇일까요?

```js
const person = {
  name: "Lee",
};

console.log(Object.getOwnPropertyDescriptor(person, "name"));
```

- {value: "Lee", writable: true, enumerable: true, configurable: true}

### 3. 아래 코드의 실행 결과는 무엇일까요?

```js
const person = {
  firstName: "Ham",
  lastName: "Ster",
  get fullName() {
    return `${firstName} ${this.lastName}`;
  },
  set fullName(name) {
    [this.firstName, this.lastName] = name.split(" ");
  },
};
person.fullName = "Ham Sty";

console.log(Object.getOwnPropertyDesciptor(person, "lastName"));
console.log(Object.getOwnPropertyDesciptor(person, "fullName"));
```

- {value: "Sty", writable: true, enumerable: true, configurable: true}
- {get: f, set: f, enumerable: true, configurable: true}

### 4. 객체 확장 금지(Object.preventExtensions), 객체 밀봉(Object.seal), 객체 동결(Object.freeze)을 비교하는 표가 아래에 주어졌습니다. 빈칸에 O, X를 채워주세요.

| 구분           | 메서드                  | 프로퍼티 추가 | 프로퍼티 삭제 | 프로퍼티 값 읽기 | 프로퍼티 값 쓰기 | 프로퍼티 어트리뷰트 재정의 |
| -------------- | ----------------------- | ------------- | ------------- | ---------------- | ---------------- | -------------------------- |
| 객체 확장 금지 | Object.preventExtension |               |               |                  |                  |                            |
| 객체 밀봉      | Object.seal             |               |               |                  |                  |                            |
| 객체 동결      | Object.freeze           |               |               |                  |                  |                            |

| 구분           | 메서드                  | 프로퍼티 추가 | 프로퍼티 삭제 | 프로퍼티 값 읽기 | 프로퍼티 값 쓰기 | 프로퍼티 어트리뷰트 재정의 |
| -------------- | ----------------------- | ------------- | ------------- | ---------------- | ---------------- | -------------------------- |
| 객체 확장 금지 | Object.preventExtension | X             | O             | O                | O                | O                          |
| 객체 밀봉      | Object.seal             | X             | X             | O                | O                | X                          |
| 객체 동결      | Object.freeze           | X             | X             | O                | X                | X                          |
