# [21] 빌트인 객체

### 1. 자바스크립트의 객체는 크게 `표준 빌트인 객체(standard built-in objects/native objects/global objects)`, `호스트 객체(host objects)`, `사용자 정의 객체(user-defined objects)` 3가지로 분류할 수 있어요. 이 중 `표준 빌트인 객체`에 대해서 설명해주세요.

- 표준 빌트인 객체는 ECMAScript 사양에 정의된 객체를 말하며, 애플리케이션 전역의 공통 기능을 제공한다. ECMAScript 사양에 정의된 객체이므로 자바스크립트 실행환경(브라우저 환경 또는 Node.js 환경)과 관계없이 언제든지 사용할 수 있다. 표준 빌트인 객체는 전역 객체의 프로퍼티로서 제공된다. 따라서 별도의 선언 없이 전역 변수처럼 언제나 참조할 수 있다.

### 2. 자바스크립트의 객체는 크게 `표준 빌트인 객체(standard built-in objects/native objects/global objects)`, `호스트 객체(host objects)`, `사용자 정의 객체(user-defined objects)` 3가지로 분류할 수 있어요. 이 중 `호스트 객체`에 대해서 설명해주세요.

- 호스트 객체는 ECMAScript 사양에 정의되어 있지 않지만, 자바스크립트 실행 환경(브라우저 환경 또는 Node.js 환경)에서 추가로 제공되는 객체를 말한다.
- 브라우저 환경에서는 DOM, BOM, Canvas, XMLHttpRequest, fetch, requestAnimationFrame, SVG, Web Storage, Web Component, Web Worker와 같은 클라이언트 사이드 API를 호스트 객체로 제공하고, Node.js 환경에서는 Node.js 고유의 API를 호스트 객체로 제공한다.

### 3. 아래 코드의 실행 결과와 왜 그런지 설명해주세요.

```js
const str = "hello";
str.name = "Lee";
console.log(str.name);
```

- undefined
- 원시값을 객체처럼 사용하면 자바스크립트 엔진은 암묵적으로 연관된 객체를 생성하여 생성된 객체로 프로퍼티에 접근하거나 메서드를 호출하고 다시 원시값으로 되돌린다.
- 3번 라인에서 호출 객체는 2번 라인에서 호출된 것과 다른 래퍼 객체를 가리킨다.

### 4. 아래 코드의 실행 결과는 무엇일까요?

```js
console.log(parseInt("10.7"));
```

- 10

### 5. 아래 코드의 실행 결과는 무엇일까요?

```js
console.log(typeof Infinity);
```

- number

### 6. 아래 코드의 실행 결과는 무엇일까요?

```js
console.log(typeof NaN);
```

- number

### 7. 빌트인 전역 함수 중 `encodeURI`와 `encodeURIComponent`의 차이에 대해서 설명해주세요.

- encodeURI는 완전한 URI(Uniform Resource Identifier)를 문자열로 전달받아 이스케이프 처리를 위해 인코딩한다.
- encodeURIComponent는 URI 구성 요소(component)를 인수로 전달받아 인코딩한다.
- encodeURIComponent 함수는 인수로 전달된 문자열을 URI의 구성요소인 쿼리 스트링의 일부로 간주한다. 따라서 쿼리스트링 구분자로 사용되는 `=`, `?`, `&`까지 인코딩한다. 반면 encodeURI 함수는 매개변수로 전달된 문자열을 완전한 URI 전체라고 간주한다. 따라서 쿼리 스트링 구분자로 사용되는 `=`, `?`, `&`은 인코딩하지 않는다.

### 8. 다음 코드의 실행 과정을 설명해주세요.

```js
const str = "sohee";

console.log(str.toUpperCase()); // SOHEE
```

- 자바스크립트 엔진이 임시객체인 래퍼 객체를 생성
- 할당된 문자열 sohee는 래퍼 객체의 [[StringData]] 내부 슬롯에 할당
- 래퍼 객체의 메서드인 toUpperCase를 호출함
- 코드 실행 후 래퍼 객체를 다시 원시값으로 되돌리고 래퍼 객체는 가비지 컬렉션의 대상이 됨

### 9. 원시값 중 래퍼객체를 생성하지 않는 값에는 무엇이 있나요?

- null, undefined

### 10. `eval` 함수는 기존의 스코프를 언제 수정하나요?

- 런타임에 동적으로 수정

### 11. 다음 코드의 실행 결과는 무엇인가요?

```js
isNaN(10);
isNaN("10");
isNaN("hello");
isNaN(true);
isNaN(false);
isNaN(undefined);
isNaN({});
isNaN(new Date());
```

- false, false, true, false, false, true, true, false

### 12. 다음 코드의 실행 결과는 무엇인가요?

```js
parseInt("10");
parseInt("10", 2);
parseInt("0xf");
parseInt("f", 16);
parseInt("1A0");
parseInt("58", 8);
parseInt("11 22 33");
parseInt("Mickey 17");
```

- 10, 2, 15, 15, 1, 5, 11, NaN
