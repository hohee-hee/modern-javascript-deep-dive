**[21] 빌트인 객체 (6문항)**

1. 다음 코드의 실행 과정을 설명해주세요.

```js
const str = "sohee";

console.log(str.toUpperCase()); // SOHEE
```

    1. 자바스크립트 엔진이 임시객체인 래퍼 객체를 생성
    2. 할당된 문자열 `sohee`는 래퍼 객체의 `[[StringData]]` 내부 슬롯에 할당
    3. 래퍼 객체의 메서드인 `toUpperCase`를 호출함
    4. 코드 실행 후 래퍼 객체를 다시 원시값으로 되돌리고 래퍼 객체는 가비지 컬렉션의 대상이 됨

2. 원시값 중 래퍼객체를 생성하지 않는 값에는 무엇이 있나요?

- `null`, `undefined`

3. `eval` 함수는 기존의 스코프를 언제 수정하나요?

- 런타임에 동적으로 수정

4. 다음 코드의 실행 결과는 무엇인가요?

   ```js
   isNaN(10); // false
   isNaN("10"); // false
   isNaN("hello"); // true
   isNaN(true); // false
   isNaN(false); // false
   isNaN(undefined); // true
   isNaN({}); // true
   isNaN(new Date()); // false
   ```

5. 다음 코드의 실행 결과는 무엇인가요?

   ```js
   parseInt("10"); // 10
   parseInt("10", 2); // 2
   parseInt("0xf"); // 15
   parseInt("f", 16); // 15
   parseInt("1A0"); // 1
   parseInt("58", 8); // 5
   parseInt("11 22 33"); // 11
   parseInt("Mickey 17"); // NaN
   ```

6. `encodeURI`와 `encodeURIComponent`는 전달받은 문자열을 각각 어떤 것으로 간주하여 인코딩하나요?
   - `encodeURI` : 완전한 URI로 간주 -> 쿼리스트링 구분자로 사용되는 `=`, `?`, `&`는 인코딩하지 않음
   - `endcodeURIComponent` : 쿼리스크링으로 간주 -> 쿼리스트링 구분자로 사용되는 `=`, `?`, `&`도 인코딩
