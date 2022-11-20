# Utlity Types

-   keyof
    -   interface의 key값들을 union형태로 받을 수 있다
    -   ```ts
        type UserKey = keyof USer;
        ```
-   Partial<.T>
    -   Partial은 propoty들을 모두 opctional로 바꿔준다
    -   ```ts
        let admin: Partial<User> = {
            id: 121321,
            name: 'Bobbb',
        };
        ```
-   Required<.T>
    -   Required는 Patial과는 반대로 모두 적어주어야한다
    -   ```ts
        let admin: Required<User> = {
            id: 121321,
            name: 'Bobbb',
            age: 17,
        };
        ```
-   Readonly<.T>
    -   Readonly는 처음만 할당이 가능하고 그 후로는 불가하다
    -   ```ts
        let admin: Readonly<User> = {
            id: 121321,
            name: 'Bobbb',
            age: 17,
        };
        admin.id = 4; // 오류
        ```
-   Record<K,T>
    -   Record에서 k는 key고 t는 type이다
    -   ```ts
        type Grade = '1' | '2' | '3';
        type Score = 'A' | 'B' | 'C' | 'D';
        const score: Record<Grade, Score> = {};
        ```
-   Pick<K,T>
    -   interface에서 필요한 것만 뽑아 사용이 가능하다
    -   ```ts
        let admin: Pick<User, 'id' | 'name'> = {
            id: 121321,
            name: 'Bobbb',
        };
        ```
-   Onut<K,T>
    -   Omit은 Pick과 반대로 특정 propoty를 생략할 수 있다
    -   ```ts
        let admin: Omit<User, 'age' | 'gender'> = {
            id: 121321,
            name: 'Bobbb',
        };
        ```
-   Exclude<T1,T2>
    -   Type1에서 Type2타입을 제거한다
    -   ```ts
        type t1 = string | number;
        type t2 = Exclude<t1, number>;
        ```
-   NonNullable<Type>
    -   Null을 제외한 타입을 생성한다 undefined도 마찬가지이다
    -   ```ts
        type t1 = string | number | null;
        type t2 = NonNullable<T1>;
        ```
