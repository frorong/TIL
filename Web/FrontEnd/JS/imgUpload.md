# 이미지 업로드하기
1. input 태그의 타입을 file로 지정
```html
<input type="file">
<img src="">
```

2. file 주소 가져오기
```js
let selectFile = document.querySelector("input").files[0];
```

3. 화면에 뿌리기
```js
let selectFile = document.querySelector("input").files[0];
const file = URL.createObjectURL(selectFile);
document.querySelector("img").src = file;
```
