# Ts 설치

### 설치

-   글로벌 설치

```
npm install -g typescript
```

-   로컬 설치

```
npm install typescript
```

### 설치 확인

-   글로벌

```
tsc -v
```

-   로컬

```
npx tsc -v
```

### tsconfig.json

-   글로벌

```
tsc --init
```

-   로컬

```
npx tsc --init
```

-   설정

```
{
    "compilerOptions": {
        "strict": true,
        "module": "commonjs",
        "moduleResolution": "node",
        "lib": ["es2015","es2016","es2017","es2018","es2019","es2020"],
        "target": "ES5",
        "outDir": "./dist",
        "esModuleInterop": true
    },
    "exclude": ["node_modules"],
    "include": ["src/**/*"]
}
```

### Ts -> Js

-   글로벌

```
tsc
```

-   로컬

```
npx tsc
```

-   outDir로 설정해둔 경로에 js파일이 들어간다
-   -w를 붙이면 ts파일을 수정하는 동시에 적용이 된다
