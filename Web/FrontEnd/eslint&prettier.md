# ESLint&Prettier

-   ### ESLint
    -   코드 퀄리티를 보장해준다
    -   코드를 작성하는데에 여러 방식이 있는데 일관성 있는 방식으로 코드를 구현할 수 있도록 잡아준다
-   ### Prettier
    -   코드 스타일을 깔끔하고 통일되게 해준다
    -   코드 구현 방식이 아닌 텍스트를 깔끔하게 잡아준다

## ESLint 세팅

-   설치
    -   `npm install -D eslint`
    -   `yarn add -D eslint`
-   ESLint extention도 설치 해야한다
-   필요에 따라 .eslintrc 파일이 필요할 수 있다
-   ESLint는 VSCode 에디터에 적용해서 사용하는 것이기 때문에 모두 설치 및 세팅이 되어야 한다  
    설치가 되었다면 .eslintrc 파일을 통해 세팅을 해주어야 한다

### .eslintrc

아래는 eslint Doc에 나와있는 예라고 한다

```
{
    "root": true,
    "plugins": [
        "@typescript-eslint"
    ],
    "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended"
    ],
    "parser": "@typescript-eslint/parser",
    "rules": {
        "@typescript-eslint/strict-boolean-expressions": [
            2,
            {
                "allowString" : false,
                "allowNumber" : false
            }
        ]
    }
}
```

-   root의 값이 true가 아니면 내 pc의 root 디렉토리까지 eslint를 찾는다
-   plugins는 여러가지가 있고 대표적으로는 아래 정도가 있다고 한다
    -   ```
        eslint-config-airbnb-base: 에어비엔비 린트 플러그인
        eslint-config-next: Next.js 전용 린트 플러그인
        eslint-plugin-react: 리액트 전용 플러그인
        eslint-plugin-prettier: 린트 위에 사용할 프리티어 플러그인
        eslint-config-prettier: 요건 린트 설정과 중복되는 부분이 있으면 프리티어 룰에서 제외하는 플러그인
        @typescript-eslint/eslint-plugin: : 타입스크립트 전용 린트
        ```
    -   각 플러그인은 npm이나 yarn으로 설치하면 된다
-   parser는 각 코드 파일을 검사할 파서를 설정하는 부분이다  
    특정 플러그인을 사용한다면 해당 플러그인에서 제공하는 paser를 사용하면 된다
-   extends 외부 파일을 확장하는 부분이다  
    사용하려는 플러그인에서 기본적으로 제공하는 rule set이 적용된다고 한다
-   rules 직접 lint rule을 적용하는 부분이다

-   ## Prettier 세팅

1. VSCode extention을 설치한다
2. prettier 플러그인을 설치하고 VSCode에 세팅한다

-   위와 같이 2가지 방법이 있다

-   VSCode의 setting에서 prettier을 설정할 수 있다

    -   npm이나 yarn으로 prettier을 받았다면 ` .prettierrc`파일을 꼭 사용해야 한다
    -   ` .prettierrc`파일이 있으면 그 파일로 룰이 적용된다

-   ## VSCode Settings.json

    저장시 자동으로 린트를 잡아주려면 설정을 해주어야한다

-   @
-   ```
    npm install eslint prettier eslint-config-prettier eslint-plugin-prettier --save-dev
    ```
-   .eslintrc.json
    -   ```
        {
          "extends": ["plugin:prettier/recommended"]
        }
        ```
-   Preferences: Open Settings
    -   ```
        {
          "editor.defaultFormatter": "esbenp.prettier-vscode",
          "editor.formatOnSave": true,
          "editor.codeActionsOnSave": {
              "source.fixAll.eslint": true
          },
        }
        ```
