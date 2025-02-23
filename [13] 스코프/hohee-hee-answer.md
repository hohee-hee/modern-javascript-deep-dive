1. 다음 함수의 실행 결과는 무엇인가요?

```javascript
var x = 10;

function foo() {
  console.log(x);
  var x = 20;
}

foo();
```

- `undefined`: `foo`에서 `x`가 호이스팅 발생 / 할당 전이므로 `undefined`

2. 자바스크립트에서는 언제 상위스코프가 결정되나요?

- 함수 정의가 실행될 때
