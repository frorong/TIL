# js로 구글 검색 기능 만들기!

난이도가 꽤 있을거라 생각했는데 굉장히 간단했다
```
https://www.google.com/search?q=blabla
```
링크만 수정해주면 알아서 검색이 되는것!

```js
const App = () => {
    const [value, setValue] = useState('');
    const [url, setUrl] = useState('');
    const onClick = () => {
        setUrl(`https://www.google.com/search?q=${value}`);
        window.open(url);
    }
    const onChange = (e) => {
        setValue(e.target.value);
    }
    return(
        <div>
            <input placeholder="검색어 입력" onChange={onChange}/>
            <button onClick={onClick}>검색</button>
        </div>
    )
}
``` 
이렇게만 해도 되지 않을까?  
다음에 프로젝트 할 때 시도 해봐야겠다