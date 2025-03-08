# [22] this

### 1. this는 무엇인가요?

- this는 자신이 속한 객체 또는 자신이 생성할 인스턴스를 가리키는 자기 참조 변수(self-referencing variable)다. this를 통해 자신이 속한 객체 또는 자신이 생성할 인스턴스의 프로퍼티나 메서드를 참조할 수 있다.

### 2. this 바인딩은 무엇인가요?

- 바인딩은 식별자와 값을 연결하는 과정을 의미한다. this 바인딩은 this(키워드로 분류되지만 식별자 역할을 한다)와 this가 가리킬 객체를 바인딩하는 것이다.

### 3. strict mode가 아닌 경우 일반 함수로 호출된 함수의 this에는 무엇이 바인딩되나요?

- 전역 객체

### 4. 메서드 내부의 this에는 무엇이 바인딩되나요?

- 메서드를 호출한 객체

### 5. 생성자 함수 호출 시 this에는 무엇이 바인딩되나요?

- 생성자 함수가 (미래에) 생성할 인스턴스

### 6. `Function.prototype.apply`, `Function.prototype.call`, `Function.prototype.bind` 메서드에 의한 간접 호출에 의해서는 this에 무엇이 바인딩되나요?

- `Function.prototype.apply/call/bind`메서드에 첫 번째 인수로 전달한 객체

### 7. strict mode가 적용 되었을 때와 아닐 때, 아래 코드를 브라우저에서 실행시킬 때의 결과는 무엇인가요?

```js
function foo() {
  console.dir(this);
}

foo();
```

- undefined, Window

### 8. 다음 코드를 브라우저 환경에서 실행시켰을 때의 결과를 설명해주세요.

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

- 1, 100

### 9. `Function.prototype.call`과 `Function.prototype.bind`의 차이는 무엇인가요?

- call : 함수를 호출
- bind : 함수를 호출하지 않음 (첫 번째 인수로 전달한 값으로 this 바인딩이 교체된 함수를 새롭게 생성해 반환)

### 10. 다른 언어(C++, 자바 등)의 `this`와 자바스크립트의 `this`의 차이점은 무엇인가요?

- 다른 언어 : 언제나 클래스가 생성하는 인스턴스를 가리킴
- JS : 바인딩이 동적으로 결정
