# React Hooks

+ functional component에서 state를 가질 수 있게 해준다

## 1. Use State
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

## 4. Use Effect

state를 change할 때 마다 똑같이 function이 다시 실행된다\
=> 가끔 특정 코드의 실행을 제한하고 싶다

useEffect는 2개의 인자를 가지는 함수이다  
우리 코드가 딱 한번만 실행될 수 있도록 보호해준다
+ 첫 번째 인자는 우리가 딱 한번만 실행하고 싶은 코드이다  
+ 두 번째 인자는 변화를 지켜볼 dependency인데 변화가 생기면 첫 번째 인자인 코드가 실행된다  
두 번째 인자를 [ ]로 비워둔다면 처음 한 번만 실행된다
```js
const [value, setValue] = useState(" ");
useEffect(() => {
    console.log("실행");
}, [value]);
```
위와 같은 경우에는 value가 update될 때 마다 "실행" 이라고 찍힌다

```js
const [value, setValue] = useState(" ");
const [VALUE, SETvALUE] = useState(" ");
useEffect(() => {
    console.log("value와 VALUE가 바뀔 때 실행");
}, [value, VALUE]);
```
위와 같은 경우처럼 두 가지를 동시에 지켜볼 수도 있다

### Use Title

+ 제목을 업데이트 시켜준다
+ ```js
    const useTitle = (initialTitle) => {
    const [title, setTitle] = useState(initialTitle);
    const updateTitle = () => {
        const htmlTitle = document.querySelector("title");
        htmlTitle.innerText = title;
    }
    useEffect(updateTitle,[title])
    return setTitle;
    }

    const App = () => {
    const titleUpdate = useTitle("Loading...");
    };
    ```

#### reference
+ component의 특정 부분을 선택할 수 있는 방법

### Use Click
```js
const useClick = (onClick) => {
  const element = useRef();
  useEffect(() => {
    if(element.current){
      element.current.addEventListener("click", onClick);
    }
    return()=>{
      if(element.current){
        element.current.removeEventListener("click", onClick);
      }
    }
  },[]);
  return element;
}

const App = () => {
  const sayHello = () => console.log("say hello");
  const title = useClick();
  return (
    <div className="App">
      <h1 ref={title} >Hi</h1>
    </div>
  );
};
```