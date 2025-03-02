**[21] 빌트인 객체 (6문항)**

1. 다음 코드의 실행 과정을 설명해주세요.

```js
const str = "sohee";

console.log(str.toUpperCase()); // SOHEE
```

2. 원시값 중 래퍼객체를 생성하지 않는 값에는 무엇이 있나요?

3. `eval` 함수는 기존의 스코프를 언제 수정하나요?

4. 다음 코드의 실행 결과는 무엇인가요?

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

5. 다음 코드의 실행 결과는 무엇인가요?

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

6. `encodeURI`와 `encodeURIComponent`는 전달받은 문자열을 각각 어떤 것으로 간주하여 인코딩하나요?
