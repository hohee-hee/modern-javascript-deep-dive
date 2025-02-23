1. 다음 코드의 실행 결과와 이유유는 무엇인가요?

```js
function Circle(radius) {
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };
}

const circle1 = new Circle(5);
const circle2 = Circle(10);

console.log(circle1); // Circle {radius: 5, getDiameter: ƒ} => 생성자 함수로 객체 생성
console.log(circle2); // undefined => 함수로서 호출된 Circle은 반환문이 없음
console.log(radius); // 10 => 일반함수로 호출된 Circle 내의 this는 전역객체
```

2. 모든 함수는 callable하지만 모든 함수가 constructor인 건 아닙니다. constructor인 함수와 그렇지 않은 함수를 구분해주세요.

- constructor : 함수 선언문 , 함수 표현식, 클래스
- non-constructor : 메서드, 화살표함수

3. `new.target`은 무엇인가요?

- new 연산자와 함께 생성자 함수로서 호출되었는지 확인하는 속성
