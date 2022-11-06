# Ajax

### Ajax란?
+ 서버에 새로고침 없이 연결을 도와준다


### 사용
+ jQuery를 설치하여 $ajax()를 사용한다
+ axios를 설치하여 axios.get()을 사용한다
+ fetch를 사용한다

+ axios는 React나 Vue에서 호환성이 좋아 자주 사용된다고 한다

### 설치
+   ```
    yarn add axios
    ```
+   ```
    npm install add axios
    ```
+ import 
    ```
    import axios from 'axios';
    ```

### 사용
```js
ulr = "https://blablablablablablabla"
axios.get(url)
  .then((res)=>{
    console.log(res.data);
  })
  .catch(()=>{
    console.log('fail');
  })
```
사용 방법은 fetch와 비슷해 보인다