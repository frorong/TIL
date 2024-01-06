# Literal Types

### 정의

```ts
const constName = 'constName';
let letName = 'letName';
```

-   constName은 바뀔 수 없는 값이기 때문에 타입이 constName이다
-   letName은 바뀔 수 있기 때문에 string 타입이다

-   여러 타입을 지정하려면 ' | ' 를 써준다 (유니온타입)

```ts
let letName: string|number = "letName';
```

---

-   타입을 만들 수 있다

```ts
type Job = 'fisher' | 'developer' | 'mangnani';
interface User {
    name: string;
    job: job;
}
const user: User = {
    name: 'userName',
    job: 'developer',
};
```

-   job은 지정된 타입만 가능하다

---

-   ' & ' 로 인터페이스를 합칠 수 있다

```ts
interface Pig {
    name: string;
    eat():void;
}
interface Gini {
    name: string;
    color: string;
    weigth: number;
}
const GiniPig: Gini & Pig = {
    name: "기니피그",
    eat(){};
    color: yellow,
    weigth: 30,
}
```

-   여러개의 타입을 하나로 합치려면 각 요소를 모두 정의해 주어야 한다
