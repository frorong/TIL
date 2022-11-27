# prop types

prop을 보낼 때 타입을 잘못 보내는 실수를 할 수 있다\
PropType은 어떤 타입의 prop을 받고 있는지 체크해준다

```html
<script src="https://unpkg.com/prop-types@15.6/prop-types.js"></script>
```

ex

```js
Component1.propTypes = {
    text: PropTypes.string,
    fontSize: PropTypes.number,
};
```

위와 같이 작성할 수 있다\
그럼 경고 문구를 볼 수 있다\
Warning: Failed prop type: Invalid prop `fontSize` of type `string` supplied to `BTN`, expected `number`.  
 at BTN (<anonymous>:18:21)  
 at App (<anonymous>:42:31)  
printWarning @ react.development.js:245

(fontsize는 string이었지만 number를 원한다)

array, func, bool, number, object, string, symbol, node, element, 등 다양하게 적용 가능하다

확실하게 하고싶다면 뒤에 isRequired를 붙여주면 된다\
 ex

```js
Component1.propTypes = {
    text: PropTypes.string.isRequired,
    fontSize: PropTypes.number,
};
```

이 경우에는 text는 필수고 number는 선택이다

#### 만약 prop이 존재하지 않는다면 default값을 줄 수 있다

ex

```js
function Component({ text, number = 15 }) {}
```

number의 기본값은 15가 된다.

### prop types checking

```cmd
npm i prop-types
```

prop-types를 install해준다\
install이 되었다면 proptypes를 inport한다

```js
import PropTypes form "prop-types";
```
