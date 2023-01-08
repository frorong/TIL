# 폼

## 제어 컴포넌트

react에 의해 값이 제어되는 입력 폼 엘리먼트를 제어 컴포넌트 라고 한다

### textarea 태그

textarea 엘리먼트는 텍스트를 자식으로 정의한다

```js
return <textarea value={this.state.value} onChange={this.handleChange} />;
```

react에서 textarea는 value 어트리뷰트를 대신 사용한다

### select 태그

```js
return (
    <select value={this.state.value} onChange={this.handleChange}>
        <option value="grapefruit">Grapefruit</option>
        <option value="lime">Lime</option>
        <option value="coconut">Coconut</option>
        <option value="mango">Mango</option>
    </select>
);
```

react에서는 selected 어트리뷰트를 사용하는 대신 최상단 select태그에 value 어트리뷰트를 사용한다
