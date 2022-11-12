# Types

## 기본 타입 정의

-   ### 선언

```ts
let str: string;
let bool: boolean;
```

-   이렇게 하면 오류가 난다

```ts
str = 1;
bool = 'string';
```

-   ### 배열 선언

```ts
let arr: number[];
```

```ts
let arr: Array<number>;
```

-   ### 튜플
-   인덱스별로 타입 지정이 가능하다

```ts
let arr[string, number];
```

-   ### 반환값

```ts
function func(): void {}
```

-   오류를 반환하거나 영원히 반복되는 함수의 경우 never를 사용한다

```ts
function func ():never{
    throw new Error();
}
-------------------------
function func ():never{
    while(true){

    }
}
```

-   ### enum
-   비슷한 값끼리 묶어둔다
-   enum에 새로운 값을 주지 않으면 자동으로 0부터 1씩 할당된다

```ts
enum Os{
    Window = 1;
    Android = 5;
    Ios = 9;
}
```

-   아래와 같이 하면 OS에는 윈도우 안드로이드 아이오에스만 들어갈 수 있다

```ts
enum Os{
    Window = 1;
    Android = 5;
    Ios = 9;
}
let OS:Os;
OS = Os.Android;
```

### null, undefined

```ts
let a: undefined = undefined;
let b: null = null;
```
