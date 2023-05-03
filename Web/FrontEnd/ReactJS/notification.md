# Notification

React useRef에서 notification을 지원한다  
하지만 지원하지 않는 브라우저도 있다는 사실을 기억해야한다  
또한 지속적으로 알림이 오는 서비스의 경우에는 알림이 오되 너무 많은 알림이 오지 않도록 고려해야한다

```js
const notificationRef = useRef(null);
```

간단하게 실행시킬 수 있다

```js
notificationRef.current = new Notification(title, opction);
```

알림 권한 허용

```js
Notification.requestPermission().then((permission) => {
    if (permission !== 'granted') return;
}
```

알림 클릭 화면 이동

```js
notificationRef.current.onclick = (event) => {
  event.preventDefault();
  window.focus();
  notificationRef.current.close();
};
```
