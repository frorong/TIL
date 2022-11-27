# useEffect

state를 change할 때 마다 똑같이 function이 다시 실행된다\
=> 가끔 특정 코드의 실행을 제한하고 싶다

useEffect는 2개의 인자를 가지는 함수이다  
우리 코드가 딱 한번만 실행될 수 있도록 보호해준다

-   첫 번째 인자는 우리가 딱 한번만 실행하고 싶은 코드이다
-   두 번째 인자는 변화를 지켜볼 dependency인데 변화가 생기면 첫 번째 인자인 코드가 실행된다  
    두 번째 인자를 [ ]로 비워둔다면 처음 한 번만 실행된다

```js
const [value, setValue] = useState(' ');
useEffect(() => {
    console.log('실행');
}, [value]);
```

위와 같은 경우에는 value가 update될 때 마다 "실행" 이라고 찍힌다

```js
const [value, setValue] = useState(' ');
const [VALUE, SETvALUE] = useState(' ');
useEffect(() => {
    console.log('value와 VALUE가 바뀔 때 실행');
}, [value, VALUE]);
```

위와 같은 경우처럼 두 가지를 동시에 지켜볼 수도 있다

#### Cleanup function

react.js는 component가 destory될 때도 코드를 실행시킬 수 있다

```js
function Component() {
    useEffect(() => {
        console.log('hi');
        return () => console.log('bye');
    }, []);
}
```

Component가 rendering될 때 "hi"가 찍히고 destory될 때 "bye"가 찍힌다\
화살표 함수는 간편하다
