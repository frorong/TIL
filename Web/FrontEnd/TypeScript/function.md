# Function

-   ts에서의 함수

```ts
function func(name?: string): string {
    //name이라는 매개변수는 옵셔널이고 string 타입이다
    return `Hello ${name || 'world'}`; // name이 있을 때는 name을 반환하고 아니면 world를 반환한다
}
```

-   선택적 매개변수는 필수 매개변수보다 앞에 올 수 없다

---

-   여러 타입의 매개변수를 선언할 때는 다음과 같이 작성한다

```ts
function func(name: string | undefined): string {
    return `Hello ${name || 'world'}`;
}
```

-   배열의 모든 값을 더하는 코드

```ts
function add(...nums: number[]) {
    // 들어오는 값들을 배열로 만들어준다
    return nums.reduce((result, num) => result + num, 0); // initialValue의 값은 0이다
}
```

-   bind 사용

```ts
interface User {
    name: string;
}
const Sam: User = { name: 'Sam' };
function showName(this: USer) {
    console.log(this.name);
}
const a = showName.bind(Sam);
```

-   동일한 함수지만 매개변수에 따라 다른 값을 반환할시 오버로드를 사용하여 지정 가능
