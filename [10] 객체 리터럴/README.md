# [10] 객체 리터럴

### 1. 객체에 존재하지 않은 프로퍼티에 접근하면 어떤 에러가 발생하나요?

- undefined 반환

### 2. 객체는 프로퍼티와 메서드로 구성된 집합체입니다. 프로퍼티와 메서드가 무엇인지 설명해주세요.

- 프로퍼티 : 객체 내부에서 함수 이외의 값이 할당된 프로퍼티
- 메서드 : 함수

### 3. 아래 코드의 실행 결과는 무엇일까요?

```js
var foo = {
  name: "Lee",
  name: "Kim",
};

console.log(foo);
```

- `{ name: 'Kim' }`

### 4. 아래 코드를 실행하면 어떻게 될까요?

```js
var person = {
  name: "Lee",
};

console.log(person.age);
```

- Reference Error

### 5. 아래 코드를 실행하면 어떻게 될까요?

```js
var person = {
  name: "Lee",
};
person.age = 20;
delete person.age;
delete person.address;

console.log(person);
```

- `{ name: 'Lee' }`
