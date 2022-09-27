# Gsap
+ GSAP은 js 라이브러리 이다  
복잡한 애니메이션 효과도 간단하게 줄 수 있다

## 설치
+ 공식 사이트에서 다운로드 받거나 아래와 같이 입력하여 받을 수 있다
```
npm install gsap
```

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/gsap.min.js"></script>
```


## 사용
+ gsap.to()  
gsap to는 2가지 인자를 받는다  
첫 번째 인자는 이동하고자 하는 대상이고 두 번째 인자는 동작이다
```js
gsap.to(
    ".object",{
        x:num
    }
)
```
위와 같이 입력하면 object라는 클래스를 가진 대상이 x축 방향으로 200px만큼 이동하게 된다

여기에 opacity, rocate, scale등 다양한 속성을 줄 수 있다

+ from, fromTo, set
from은 to와 정반대로 시작값을 정하고 fromTo는 from에서 시작해서 to로 끝난다  
set은 즉시 변경된다

+ play, pause, resume, reverse, restart  
애니매이션 실행, 재실행, 중지등의 기능도 지원된다

+ TimeLine  
애니메이션을 순차적으로 실행시킬 수 있는 기능이다
```js
let tl = gsap.timeline();
tl.to(".ob1",{
    x:200
})
tl.to(".ob2",{
    x:200
})
tl.to(".ob3",{
    x:200
})
```
위와 같이 사용된다