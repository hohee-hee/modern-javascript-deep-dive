# [14] 전역 변수의 문제점

### 1. 다음 코드의 실행 결과는 무엇인가요?

```js
(function () {
  var foo = 100;
})();

console.log(foo);
```

- ReferenceError

### 2. 전역변수는 스코프 체인에서 어디에 있나요? 그리고 그 위치로 인해 발생할 수 있는 문제점은 무엇인가요?

- 스코프 체인 상에서 종점에 존재, 변수 중 전역 변수의 검색 속도가 가장 느림

### 3. 전역변수와 지역변수는 각각 언제 생성되고 언제까지 유효하나요?

- 전역변수 : 코드 실행 이전에 생성되어 웹페이지를 닫을 때까지 유효 === 전역객체의 생명주기와 일치
- 지역변수 : 해당 변수가 속한 스코프의 생명주기를 따름

### 4. 다음 코드의 실행 결과가 무엇일까요?

```js
var x = "global";
function foo() {
  console.log(x);
  var x = "local";
}

foo();
console.log(x);
```

- undefined, global 출력

### 5. 전역 변수의 문제점에는 어떤 것이 있는지 설명해주세요.

- 긴 생명 주기(메모리 리소스도 오랜 기간 소비)
- 스코프 체인 상에서 종점에 존재(변수 중 전역 변수의 검색 속도가 가장 느림)
- 네임스페이스 오염(파일이 분리되어 있다해도 하나의 전역 스코프를 공유한다기 때문에, 다른 파일 내에서 동일한 이름으로 명명된 전역 변수나 적역 함수가 같은 스코프 내에 존재하는 경우)

### 6. 다음 코드의 실행 결과가 무엇일까요?

```js
var Counter = (function () {
  var num = 0;

  return {
    increase() {
      return ++num;
    },
    decrease() {
      return --num;
    },
  };
})();

console.log(Counter.num);
console.log(Counter.increase());
console.log(Counter.increase());
console.log(Counter.decrease());
console.log(Counter.decrease());
```

- undefined, 1, 2, 1, 0
