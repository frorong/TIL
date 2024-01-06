# Interface

-   아래와 같이 사용하면 오브젝트에 특정 속성값에 대한 정보가 없기 때문에 오류가 발생한다  
    때문에 interface를 사용한다

```ts
let user: object; // 객체로 정의
user = {
    name: '이름',
};
console.log(user.name);
```

-   아래와 같이 사용한다

```ts
interface User {
    name: string;
    age: number;
}
let user: User = {
    name: '이름',
    age = 00,
};
console.log(user.name);
```

-   입력값이 필수가 아닌 요소는 ?를 붙여준다?

```ts
interface User {
    name: string;
    gender?: string;
}
```

-   참조만 가능한 요소는 readonly를 붙여준다

```ts
interface User {
    name: string;
    readonly score: number;
}
```

-   key 설정

```ts
interface User {
    name: string;
    [grade: number]: string;
}
```

-   원하는 값만

```ts
type Score = 'a':'b':'c':'f';
interface User{
    name : string;
    [grade : number] : Score;
}
```

-   interface로 함수 정의

```ts
interface Add {
    (num1: number, num2: number): number;
}

const add: Add = function (x, y) {
    return x + y;
};

interface IsAdult {
    (age: number): boolean;
}

const a: IsAdult = (age) => {
    return age > 19;
};
```

-   interface로 class 정의

```ts
interface Sheep {
    color: string;
    woolLength: number;
    run(): void;
}
class Lamb implements Sheep {
    color;
    woolLength;
    constructor(c: string, wl: number) {
        this.color = c;
        this.woolLength = wl;
    }
    run() {
        console.log('새끼 양이 달립니다');
    }
}
const lamb = new Lamb('하얀색', 3);
lamb.run();
```

-   extends

```ts
interface Sheep {
    color: string;
    woolLength: number;
    run(): void;
}

interface adultSheep extends Sheep {
    hornLength: number;
    eat(): void;
}

const oldSheep: adultSheep = {
    hornLength: 20,
    eat() {
        console.log('늙은 양이 먹습니다');
    },
    color: '검은색',
    woolLength: 6,
    run() {
        console.log('늙은 양이 달립니다');
    },
};
```

-   extends는 여러개도 가능하다
