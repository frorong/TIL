# 이벤트 처리하기

React에서 event 처리

```js
return <div onClick={() => {}}>Button</div>;
```

-   react에서는 false를 return해도 기본 동작을 방지할 수 없다 preventDefault를 호출해야한다

### 이벤트 핸들러에 인자 전달하기

```js
return(
    <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
    <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
)
```

-   두 코드 모두 모두 모두 작동한다
