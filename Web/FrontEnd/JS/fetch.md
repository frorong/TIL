# fetch()

### fetch 함수를 사용하여 원격 api를 가져올 수 있다

fetch 함수는 첫 번째 인자로 api주소를 받고 두 번째 인자로 옵션을 받는다(2번째 인자는 필수가 아니다)
```js
fetch("api주소", 옵션); 
```
fetch함수는 promise타입의 객체를 반환한다  
반환된 promise객체로부터 then메소드를 사용하여 응답 객체를 얻을 수 있다
```js
fetch("api주소").then(respons => console.log(respons)); 
```

### get 방식 api호출
json이라는 함수를 사용하여 json함수가 반환하는 값을 얻는다
```js
fetch("api주소").then(res => res.json).then(data => console.log(data));
```
최종적으로 api가 제공하는 정보를 얻게 된다

### post 방식 api 호출
post방식으로 호출할 때에는 두 번째 옵션 인자가 매우 중요하다
```js
fetch('api',{
    method: 'POST',
    headers: {'Content-Type': 'application/json'},
    body: JSON.stringify({
        bla:blabla,
        blblbla:blablablabl,
    })
})
```
위와 같이 해야 서버에서 우리가 보내는 데이터가 json형태임을 알 수 있다.  
body는 반드시 string형식으로 한다.