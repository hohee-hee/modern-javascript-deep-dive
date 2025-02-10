# [03] 자바스크립트 개발 환경과 실행 방법

### 1. 브라우저와 Node.js 환경의 차이점을 설명해주세요.

- 브라우저 환경에서는 Client-side API를 사용할 수 있는 반면 Node.js에서는 Node.js host api를 사용할 수 있음

### 2. 다음 코드를 node.js 환경에서 실행하니 `RefereceError`가 발생했어요. 이유는 무엇이고 어떻게 하면 문제를 해결할 수 있나요?

```js
const arr = [1, 2, 3];

arr.forEach(alert);
```

- `alert`가 브라우저 내장 함수여서 Node.js 환경에서는 이해할 수 없음
- 브라우저 환경에서 실행하면 `alert` 실행 가능

### 3. 크롬 브라우저와 Node.js가 사용하고 있는 자바스크립트 엔진의 이름은 무엇일까요.

- v8엔진
