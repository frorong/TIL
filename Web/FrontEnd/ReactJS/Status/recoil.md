# Recoil

### install

```
npm install recoil
```

```
yarn add recoil
```

recoil 상태를 사용하려면 root 컴포넌트에 RecoilRoot를 넣어준다

```ts
return(
    <RecoilRoot><RecoilRoot/>
)
```

- 비동기 처리를 기반으로 한다

## Atom

Aton은 state의 일부를 나타낸다  
이 값을 읽는 컴포넌트들은 암묵적으로 Atom을 구독한다  
atom에 변화가 생기면 구독하는 컴포넌트들이 재 렌더링 된다

```js
const state = atom({
  key: "state",
  default: "",
});
```

컴포넌트가 atom을 읽고 쓰려면 useRecoilState를 사용한다

```js
function Component1() {
  const [state, setStatet] = useRecoilState(state);
}
```

## Selector

Selector는 파생된 상태의 일부를 나타낸다

```js
const stateLength = selector({
  key: "stateLength",
  get: ({ get }) => {
    const state = get(state);
    return state.length;
  },
});

const length = useRecoilValue(stateLength);
```

## 장단점

- 사용법이 간단하다
- 동시성을 지원한다
- selector를 통해 캐싱된 값을 반환

* jotai나 zustand에 비해 무겁다
* js로 작성되었다

- 업데이트가 활발하지 않다
