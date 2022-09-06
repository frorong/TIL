# React Hooks

+ functional component에서 state를 가질 수 있게 해준다

### 1. Use State
+ useState는 2개의 value를 return한다, 상태를 관리해준다
+ ``` js
    import React, { useState } from "react";

    const [key, setKey] = useState(default);
    ```

### 2. Use Input
+ useInput은 input을 업데이트 한다
+ ``` js
    const useInput = (initialValue, validator) => {
        const [value, setValue] = useState(initialValue);
        const onChange = event => {
            const {
                target: {value}
            } = event;
            let willUpdate = true;
            if(willUpdate){
                setValue(value);
            }
            if(typeof validator === "function"){
                 willUpdate = validator(value);
            };
        };
        return {value, onChange};
    };
    const App = () => {
        const maxLength = value => value.lenght < 10; //10글자 아래로 적용된다
        const name = useInput("Mr.");
        return(
            <input {...name} />
        )
    }
    ```

### 3. Use Tab
+ [->](https://github.com/Lee-Seungje/React-Hooks/blob/main/useState/useTab.js)