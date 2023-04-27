# zustand

zustand는 상태관리 라이브러리다  
대표적인 상태관리 라이브러리로는 Recoil, Redux, Jotai

zustand는 Jotai 개발자들이 만든 라이브러리라고 한다  
zustand는 쉽고 최소한의 코드로 전역 상태관리를 할 수 있다

- 설치

```
npm i zustand
```

```
yarn add zustand
```

사용

- 먼저 import를 해준다

```ts
import { create } from "zustand";
```

- 인터페이스로 타입을 설정 해준다

```ts
interface DarkState {
  isDark: boolean;
  setIsDark: (value: boolean) => void;
}
```

- 초기값 설정과 셋팅 함수 설정을 해준다

```ts
const useDarkState = create<DarkState>((set) => ({
  isDark: false,
  setIsDark: (value) => set({ isDark: value }),
}));

export default useDarkState;
```

- 이렇게 state를 불러와서 사용할 수 있다

```ts
import useDarkState from "Stores/useDarkStore";

const { isDark, setIsDark } = useDarkState();
```
