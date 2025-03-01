아래 코드의 실행 결과는 무엇일까요?
```js
const person = {
    name: 'Lee'
};

console.log(Object.getOwnPropertyDescriptor(person, 'name'));
```

아래 코드의 실행 결과는 무엇일까요?
```js
const person = {
    firstName: 'Ham',
    lastName: 'Ster',
    get fullName() {
        return `${firstName} ${this.lastName}`
    },
    set fullName(name) {
        [this.firstName, this.lastName] = name.split(' ');
    }
}
person.fullName = 'Ham Sty';

console.log(Object.getOwnPropertyDesciptor(person, 'lastName'));
console.log(Object.getOwnPropertyDesciptor(person, 'fullName'));
```

객체 확장 금지(Object.preventExtensions), 객체 밀봉(Object.seal), 객체 동결(Object.freeze)을 비교하는 표가 아래에 주어졌습니다. 빈칸에 O, X를 채워주세요.
|구분|메서드|프로퍼티 추가|프로퍼티 삭제|프로퍼티 값 읽기|프로퍼티 값 쓰기|프로퍼티 어트리뷰트 재정의|
|---|---|---|---|---|---|---|
|객체 확장 금지|Object.preventExtension||||||
|객체 밀봉|Object.seal||||||
|객체 동결|Object.freeze||||||