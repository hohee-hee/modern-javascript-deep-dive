**[17] 생성자 함수에 의한 객체 생성 (3문항)**

1. 다음 코드의 실행 결과와 이유는 무엇인가요?

```js
function Circle(radius) {
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };
}

const circle1 = new Circle(5);
const circle2 = Circle(10);

console.log(circle1);
console.log(circle2);
console.log(radius);
```

2. 모든 함수는 callable하지만 모든 함수가 constructor인 건 아닙니다. constructor인 함수와 그렇지 않은 함수를 구분해주세요.

3. `new.target`은 무엇인가요?
