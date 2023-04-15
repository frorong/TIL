# theme

emaion에서는 theme를 통해 보다 깔끔한 스타일링이 가능하다

아래는 다크모드를 구현할 때 만든 theme이다

```ts
export interface ThemeType {
  gray: readonly string[];
  primary: {
    magenta: string;
    pale_yellow: string;
  };
  secondary: {
    vivid_yellow: string;
    dusty_blue: string;
    navy_blue: string;
  };
  breakPoint: {};
  mode: {
    nav: string;
    body: string;
    footer: string;
    toggle: string;
    title: string;
    text: string;
  };
  otherProp?: any;
}

export const theme: ThemeType = {
  gray: ["#F1F1F5", "#E3E3E3", "#999999", "#636363", "#191919"],
  primary: {
    magenta: "#E23C96",
    pale_yellow: "#FFE870",
  },
  secondary: {
    vivid_yellow: "#FFE900",
    dusty_blue: "#7090B0",
    navy_blue: "#225087",
  },
  breakPoint: {},
  mode: {
    nav: "#ffffff",
    body: "#f1f1f5",
    footer: "#e3e3e3",
    toggle: "#ffffff",
    title: "#000000",
    text: "#191919",
  },
} as const;

export const darktheme: ThemeType = {
  gray: ["#F1F1F5", "#E3E3E3", "#999999", "#636363", "#191919"],
  primary: {
    magenta: "#E23C96",
    pale_yellow: "#FFE870",
  },
  secondary: {
    vivid_yellow: "#FFE900",
    dusty_blue: "#7090B0",
    navy_blue: "#225087",
  },
  breakPoint: {},
  mode: {
    nav: "#191919",
    body: "#191919",
    footer: "#636363",
    toggle: "#999999",
    title: "#ffffff",
    text: "#ffffff",
  },
} as const;
```

TS에서는 테마의 타입을 지정한다

```ts
//emotion.d.ts
import "@emotion/react";
import { ThemeType } from "./theme";

declare module "@emotion/react" {
  export interface Theme extends ThemeType {}
}
```

이런식으로 지정하면 편하게 지정이 가능하다

```ts
const Container = styled.div`
  background-color: ${(props) => props.theme.color.yellow};
`;
```

이렇게 지정이 가능하다

```ts
const Container = styled.div`
  background-color: ${({ theme: { color } }) => color.yellow};
`;
```

보다 깔끔하다
