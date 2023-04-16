# emotion

React 컴포넌트를 스타일링할 수 있는 라이브러리

### 패키지 설치

`$ npm i @emotion/react`

### 기본 문법

```js
/** @jsxImportSource @emotion/react */
import { css } from "@emotion/react";

function Component1() {
  return (
    <div
      css={css({
        backgroundColor: "red",
      })}
    >
      red area
    </div>
  );
}
```

객체형 스타일을 css()함수의 인자로 넘길 수 있다  
이 방법을 사용하면 css()함수 호출을 생략하고 css prop에 바로 객체를 넘길 수 있다

### JSX pragma

```js
/** @jsxImportSource @emotion/react */
```

위 코드 상단에 있는 이 부분은 바벨 트랜스파일러에게 react의 jsx함수를 사용하지 말고 emotion의 jsx함수를 사용하라고 알려주는 부분이다

### 고정 스타일링

```js
/** @jsxImportSource @emotion/react */
import { css } from "@emotion/react";

function Component1({ argument }) {
  return (
    <div
      css={css({
        borderRadius: "6px",
        border: "1px solid rgba(27, 31, 36, 0.15)",
        backgroundColor: "rgb(246, 248, 250)",
        color: "rgb(36, 41, 47)",
        fontFamily: "-apple-system, BlinkMacSystemFont, sans-serif",
        fontWeight: "600",
        lineHeight: "20px",
      })}
    >
      {argument}
    </div>
  );
}

export default Component1;
```

### 가변 스타일링 1

```js
/** @jsxImportSource @emotion/react */

const colors = {
  default: "rgb(36, 41, 47)",
  danger: "rgb(207, 34, 46)",
  outline: "rgb(9, 105, 218)",
};

function Button({ variant = "default" }) {
  return (
    <button
      css={{
        color: colors[variant],
      }}
    ></button>
  );
}

export default Button;
```

### 가변 스타일링 2

```js
/** @jsxImportSource @emotion/react */

const sizeStyles = {
    sm: {
        fontSize: '12px',
        padding: '3px 12px',
    },
    md: {
        fontSize: '14px',
        padding: '5px 16px',
    },
    lg: {
        fontSize: '16px',
        padding: '9px 20px',
    },
};

function Button({ size = 'md' }) {
    return (
        <button
            css={{
                ...sizeStyles[size],
            }}
        ></button>
    );
}

export default Button;



<Button size="sm" variant="default">
    Default
</Button>
<Button size="md" variant="danger">
    Danger
</Button>
<Button size="lg" variant="outline">
    Outline
</Button>
```

## ts.config

```ts
    "skipLibCheck": true, // 오류 검출이 줄어든다 -> 빨라진다
    "jsxImportSource": "@emotion/react",
     // /** @jsxImportSource @emotion/react */ 를 생략할 수 있다
```
