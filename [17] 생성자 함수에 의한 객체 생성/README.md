# [17] 생성자 함수에 의한 객체 생성

### 1. 다음 코드의 실행 결과와 이유는 무엇인가요?

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

- Circle {radius: 5, getDiameter: ƒ} => 생성자 함수로 객체 생성
- undefined => 함수로서 호출된 Circle은 반환문이 없음
- 10 => 일반함수로 호출된 Circle 내의 this는 전역객체

### 2. 모든 함수는 callable하지만 모든 함수가 constructor인 건 아닙니다. constructor인 함수와 그렇지 않은 함수를 구분해주세요.

- constructor : 함수 선언문 , 함수 표현식, 클래스
- non-constructor : 메서드, 화살표함수

### 3. `new.target`은 무엇인가요?

- new 연산자와 함께 생성자 함수로서 호출되었는지 확인하는 속성

### 4. 아래의 생성자 함수에서는 인스턴스를 초기화하는 부분이 명시되어 있지만, 인스턴스를 생성하고 반환하는 부분이 명시되어 있지 않습니다. 자바스크립트 엔진이 암묵적으로 수행하는 인스턴스 생성 및 반환 과정, 인스턴스 초기화에서 this를 사용할 수 있는 이유에 대해서 설명해주세요.

```js
function Circle(radius) {
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };
}
const circle1 = new Circle(5); // 반지름이 5인 Circle 객체를 생성
```

- 런타임 이전에 인스턴스 생성과 this 바인딩 (암묵적으로 빈 객체 생성 및 해당 인스턴스를 this에 바인딩) -> 인스턴스 초기화(생성자 함수에 기술된 초기화, 고정값 할당) -> 인스턴스 반환(완성된 인스턴스가 바인딩된 this를 반환)

### 5. 생성자 함수 선언 시에는 Pascal 케이스를 사용하는 것이 일반적입니다. 그 이유가 무엇일까요?

- javascript에서는 일반 함수와 생성자 함수 선언 시의 특별한 형식적 차이가 없기 때문에, 생성자 함수를 일반 함수와 구별하기 위해서 일반적으로 Pascal 케이스를 사용합니다.

### 6. 생성자 함수가 new 연산자 없이 호출되는 것을 방지하기 위한 방법들이 어떤 것이 있을까요?

- Pascal 케이스 컨벤션, new.target(new 연산자와 함께 호출된 경우 new.target은 함수 자신, 일반 함수로 호출된 경우 undefined), 스코프 세이프 생성자 패턴
