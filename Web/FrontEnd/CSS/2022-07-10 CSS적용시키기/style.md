### 어제(07/09) 강의를 들으며 만들어보던 JS의 기능 구현을 끝내서 오늘 CSS로 스타일링 연습을 해보았습니다
<h4>아래의  사진은 스타일링 전 화면의 모습입니다</h4>
<img src="화면 캡처 2022-07-10 초기.png">
<br>
<br>
<br>
<br>

+ css 코드
    ```css
    .hidden{display: none;} /*js에서 필요했던 옵션입니다*/
    img{width: 1920px; position: absolute; top: 0; z-index: -5; left: 0; height: 969px;}/*사진의 크기와 위치를 맞추어 주었습니다*/
    #greeting{position: absolute; top: 150px; left: 780px; font-size: 50px;}/*로그인 후 인사말의 크기와 위치를 맞추어 주었습니다*/
    #clock{position: absolute; top: 230px; left: 780px; font-size: 100px;}/*시계의 폰트 크기와 위치를 지정해 주었습니다*/
    body{color: white;}/*전체 폰트 색을 흰색으로 지정해 주었습니다*/
    #work{font-size: 35px; font-weight: bolder;}/*"오늘의 할 일"이라는 글자의 크기와 두께를 지정해 주었습니다*/
    #workspace{position: absolute; top: 600px; left: 1500px;}/*오늘의 할 일이 들어갈 p태그와 form태그가 들어간 div태그의 위치를 지정해 주었습니다*/
    #InPut{width: 200px; height: 20px; font-size: 20px; border-radius: 5px;}/*위 div태그 안의 form태그 안의 input태그의 크기와 폰트 크기를 지정해 주었습니다*/
    #todolist{font-size: 20px; color: greenyellow;} /*오늘 해야할 일 목록의 색과 폰트 크기를 지정해 주었습니다*/
    #form{position: absolute; top: 200px; left: 800px;}/*login기능이 적용된 form태그의 위치를 지정해 주었습니다*/
    #inpput{width: 300px; height: 50px; font-size: 30px; opacity:0.5; border-radius: 10px;}/*위 form태그 안의 input태그의 투명도와 테두리, 크기 등을 지정해 주었습니다*/
    button{width: 50px; height: 55px; opacity:0.5; position: absolute; top: 1px; left: 320px;
        font-size: 20px; border-radius: 10px;}/*단 하나뿐인 버튼의 크기와 투명도, 위치 등을 지정해 주었습니다*/
        /*->> 이후 버튼이 하나가 아니란걸 인지하여 id를 만들어 적용시켰습니다*/
    #quote{top: 500px; position: absolute; left: 760px; font-size: 30px;}/*명언의 크기와 위치를 지정해 주었습니다*/
    #weather{position: absolute; top: 700px; left: 780px; font-size: 40px; font-weight: bolder;}/*날씨의 크기와 두께, 위치를 지정해 주었습니다*/
    ```
<br><br>

<h4>아래의  사진은 CSS가 적용된 화면의 모습입니다</h4>
<h4>(로그인 전)</h4>
<img src="2022-07-10 css적용1.png">
<h4>(로그인, 오늘의 할 일 작성 후)</h4>
<img src="2022-07-10 css적용2.png">
<h4>(오늘의 할 일의 버튼 수정 후)</h4>
<img src="화면 캡처 2022-07-10 010426.png">