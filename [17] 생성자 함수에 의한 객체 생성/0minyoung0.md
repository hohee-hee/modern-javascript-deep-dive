아래의 생성자 함수에서는 인스턴스를 초기화하는 부분이 명시되어 있지만, 인스턴스를 생성하고 반환하는 부분이 명시되어 있지 않습니다. 자바스크립트 엔진이 암묵적으로 수행하는 인스턴스 생성 및 반환 과정, 인스턴스 초기화에서 this를 사용할 수 있는 이유에 대해서 설명해주세요.
```js
function Circle(radius) {
    this.radius = radius;
    this.getDiameter = function () {
        return 2 * this.radius;
    };
}
const circle1 = new Circle(5); // 반지름이 5인 Circle 객체를 생성
```

생성자 함수 선언 시에는 Pascal 케이스를 사용하는 것이 일반적입니다. 그 이유가 무엇일까요?

생성자 함수가 new 연산자 없이 호출되는 것을 방지하기 위한 방법들이 어떤 것이 있을까요?