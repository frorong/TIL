# Jotai

Jotai는 React 상태관리 라이브러리중 하나이다

- Typescript 기반으로 만들어져있다
- 작은 사이즈의 번들 크기를 가지고있어 가볍다

* 전역 관리 atom을 생성하고 생성된 atom을 불러와 사용한다

```js
const atom1 = atom("defaultValue"); // atom을 생성한다
const [example, setExample] = useAtom(atom1); // 생성된 atom을 불러와서 사용한다
const setExample = useSetAtom(atom1); // atom의 값을 update할 때에만 사용한다
const example = useAtomValue(atom1); // atom의 값을 read할 때에만 사용한다
```

useSetAtom, useAtomValue는 재 렌더링 되지 않는다
