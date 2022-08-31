## Style
+ 서서히 색 바꾸기
``` Css
transition: color .5s ease-in-out; /*색깔을 서서히 바꿔준다
```
+ 숨기기
```css
display: none; /*요소를 숨기게 해준다
```
+ 투명도 조절
```css
opacity:0.8; /*불투명도 80%
``` 
+ 배경에 그라데이션 적용
```css
linear-gradient(?deg, color, color); /*여러개도 가능
```
+ position
    + static : 기본값
    + relative : 원래 위치를 기준으로 이동한다
    + absolute : 부모 요소를 기준으로 이동한다, 흐름에서 벗어나 내가 원하는 곳으로 이동한다
    + fixed : 스크롤에 영향을 받지 않는다
    + sticky : 일정 범위 이상 스크롤하면 따라 내려온다
+ Invisible
    + opacity : 불투명도
    + visibility : 속성을 hidden으로 하면 기능도 적용이 안된다
    + display : 속성을 none로 하면 위치도 차지하지 않게 된다
+ reaction
    + :link : 방문하지 않은 링크
    + :visited : 방문했던 링크
    + :active : 클릭하는 순간
    + :hover : 마우스를 올려놓는 순간
+ border-style
    + solid : 직선으로
    + dotted : 점선으로
    + dashed : 큰 점선
    + double : 이중선
    + ridge : 약간의 볼록함
    + groove : 그냥 아무것도 없이  
    + inset : 안쪽으로 들어간 느낌
    + outset : 튀어나온 느낌
+ flex
    + display: flex;
    + justify-content : 주축 방향 정렬
        + space : -between : 사이에 스페이스바
    + align-items : 교차축 방향 정렬 
        + flex-start : 왼쪽으로 붙이기
        + center : 가운데로 붙이기
    + flex-direction: column : 세로로 정렬
+ 마우스 커서 바꾸기 
    + cursor : pointer;
+ 창이 작아졌을 때의 설정
```css
@media screen and (max-width: 100px) {
    
}
```
+ 스크롤바 디자인
    + ::-webkit-scrollbar : 스크롤바 전체에 대한 디자인
    + ::-webkit-scrollbar-thumb : 스크롤바 막대에 대한 디자인
    + ::-webkit-scrollbar-track : 스크롤바 막대 외부에 대한 디자인
    + 막대와 전체 사이의 간격을 투명하게
    ```css
    background-clip: padding-box;
    border: npx solid transparent;
    ```
---
vh, vw