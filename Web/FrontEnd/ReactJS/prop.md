# prop

### 동일한 스타일이지만 텍스트는 다르게

1. 원하는 스타일의 함수형 컴포넌트를 만든다
2. 함수형 컴포넌트를 호출할 때 아래와 같이 호출한다
    ```js
    return(
        <div>
            <Component1 text1:"텍스트"/>
        </div>
    )
    ```
    Component1 함수를 불러서 text1이라는 인자를 보내는 것과 같다\
    Component1 함수에서 전달받는 인자의 이름은 보통 props라고 한다
3. Component1 함수 내에서 아래와 같이 적용하면 된다
    ```js
    function Component1(props) {
        return (
            <div>
                <p>{props.text1}</p>
            </div>
        );
    }
    ```
4. 더 편하게
    ```js
    function Component1({ text1 }) {
        return (
            <div>
                <p>{text1}</p>
            </div>
        );
    }
    ```
    props는 object이기 때문에 중괄호를 이용하여 text1을 받을 수 있다
