# practicing-redux-toolkit-with-vanilla-js

# fp_tutorial

## 1강. 평가와 일급

### 평가

    - 코드가 게산되어 값을 만드는 것

### 일급

    - 값으로 다룰 수 있다.
    - 변수 담을 수 있다.
    - 함수의 인자로 사용될 수 있다.
    - 함수의 결과로 사용될 수 있다.

### 일급 함수

    - 함수를 값으로 다룰 수 있다. -> 일급 함수
    - 조합성과 추상화의 도구이다.

### 고차 함수

    - 함수를 값으로 다루는 함수

```javascript
const apply1 = (f) => f(1);
const add2 = (a) => a + 2;
log(apply1(add2)); // 3 출력
log(apply1((a) => a - 1)); // 0 출력
```

### 함수를 만들어 리턴하는 함수 (클로저를 만들어 리턴하는 함수)

```javascript
const add2 = (a) => (b) => a + 2; // closure 함수
```

## 기존과 달라진 ES6에서의 리스트 순회

```javascript
// Es5
const list = [1, 2, 3];
for (var i = 0; i < list.length; i++) {
  console.log(list[i]);
}

// Es6+
// 좀 더 선언적임
// 위 for문과 다르게 i++와 같이 구체적으로 이터레이션 도는 방식을 모르게 for문을 작성할 수 있음
for (const ele of list) {
  console.log(ele); // 1,2,3
}
```

## Array, Set, Map을 통해 알아보는 이터러블/이터레이터 프로토콜

- Set, Map의 경우에는 index로 element들 접근이 불가능하다. 근데, forOf는 돈다...?
- 좀 더 자세히 알아보자.

- Symbol.iterator가 있음
  - `Map[Symbol.iterator]`, `Set[Symbol.iterator]`

### Iterable/Iterator

- 이터러블을 리턴하는 `[Symbol.iterator]()`를 가진 값
- 이터레이터: `{ value, done }` 객체를 리턴하는 `next()`를 가진 값
