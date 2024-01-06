# 리스트와 Key

### 여러개의 컴포넌트 렌더링 하기

```js
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) => <li>{number}</li>);
```

map 메소드를 사용하여 numbers 배열을 반복 실행시켰다  
각 항목에 대해 li 엘리먼트를 반환한다

```js
return <ul>{listItems}</ul>;
```

ul 엘리먼트 안에 전체 listItems 배열을 포함할 수 있다

## Key

Key는 리액트가 어떤 항목을 변경 또는 추가할지 식별하는 것을 돕는다  
key는 배열 내부 엘리먼트에 지정해야 한다  
대부분의 경우 데이터의 ID를 key로 사용한다

### Key로 컴포넌트 추출하기

key는 주변 배열의 context에서만 의미가 있다  
배열 안에 key를 지정해야 한다

### Key는 형제 사이에서만 고유한 값이어야 한다

전체 범위에서 고유할 필요는 없다
