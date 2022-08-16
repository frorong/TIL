## function

- 기본 구조
    - function 함수 이름( 변수 이름 )
    {
        
        }
        
- 호출
    - 함수 이름(값);
- ex
    ``` JS
        const b = 0;
        function a(b)
        {
            //함수 내용
        }
        a(b);
    ```
---
## prompt
 - 기능 : 사용자에게 창을 띄워 두 가지 답을 받는다(mesege, default))
 - ex
   ``` JS
    const a = prompt("질문");
- 단점
    1. 오래된 방식이다
    2. css로 편집이 불가하다    
    3. 답을 할 때 까지 코드의 실행을 멈춘다
    > ### 비추
---
## typeof
 - 기능 : 변수의 타입을 보여준다
 - ex
    ``` JS
    console.log(typeof a);
    ```
---
## parseInt
 - 기능 
      - string을 number로 변환시킨다\
        문자를 입력하면 NaN이 나온다
 - ex
    ``` JS
    parseInt(a);
    ```
---
## isNaN
 - 기능 
    - 인자를 주면 그 인자가 number인지 아닌지 알려준다\
    (인자가 숫자면 false, 숫자가 아니면 true)
 - ex
    ``` JS
    isNaN(a);
    ```
## condition
 - ex
    ``` JS
    if(condition(true or false))
    {
        // code
    }
    else
    {
        // code
    }
    ```
    > ### c언어와 흡사
---
## getElementBy(Id, ClassName, Name, TagName . . .)
- element 가져오기
    - id 가져오기
    ``` JS
    const title = document.getElementById("title")
    title.innerText = "aaaaaaa";
    ```
    - class 가져오기
    ``` JS
    const title = document.getElementByClassName("title")
    console.log(title.className);
---
## querySelector
- element를 CSS 방식으로 검색할 수 있다\
    ex
    ``` JS
    const title = document.querySelector(.a h1); //class를 통해 찾기
    console.dir(title);
    ```
- querySelector는 첫 번째 element만 가져온다
    - 모든 element를 가져오고 싶다면 querySelectorAll을 쓴다\
        ex
    ``` JS
    const title = document.querySelectorAll(.a h1); //id를 통해 찾으려면 #을 사용, CSS 셀렉터 자체를 전달하기 때문이다
    console.dir(title);
    title.style.color = "blie" // 이런식으로 변경이 가능하다
    ```
### querySelector이 getElementBy의 상위호환급
---
### addEventListener
+ 기능 : 어떠한 이벤트가 일어났을 때 함수를 실행시킨다
+ ex
    ``` JS
    hellos.addEventListener("event", function);
    ```
+ 추가
    ``` JS
    hellos.onclick = function //이렇게도 사용이 가능하다
    //click이 일어났을 때 이 함수를 실행해 주세요 라는 것이다
    ```
+ addEventListener를 더 선호한다고 한다
+ event
    + ``` JS
        .addEventListener("click", function); // 클릭했을 때
        .addEventListener("mouseenter", function); // 마우스 커서를 댔을 때
        .addEventListener("resize", function); // 윈도우 사이즈를 조절했을 때
        .addEventListener("copy", function);  // 복사를 했을 때
        .addEventListener("offline", function);  // 인터넷 연결 해제
        .addEventListener("online", function);  // 인터넷 연결
        ```
---
### window
+ 기능 : window event가 발생하면 함수를 실행한다
+ ex
    ``` JS
    window.addEventListener("event", function);
---
### contains
+ 기능 : 명시한 class가 HTML element에 포함되어 있는지 알려준다
+ ex
    ``` JS
    h1.className.contains(Name);
    ```
---
### toggle
+ 기능 : className이 존재하는지 확인 후 존재한다면 제거, 존재하지 않으면 추가를 한다
    ```JS
    const clickedClass = "clicked"
    if(h1.classList.contains(clickedClass))
    {
        h1.classList.remove(clickedClass);
    }
    else    
    {
        h1.classList.add(clickedClass);
    }
    ```
    이 코드를 toggle 하나로 해결할 수 있다!!!
+ ex
    ``` JS
    h1.classList.toggle("clicked");
    ```
---
### preventDefault
+ 기능 : 어떤 event의 기본 행동이 발생되지 않도록 막는다
+ ex
    ```JS
    const loginForm = document.querySelector(".form");
    function onSubmit(event)
    {
        event.preventDefult(); //submit event가 실행되면 자동으로 새로고침이 된다. preventDefault 함수를 통해 새로고침을 막아줬다
        const valueOfLogin = nameLog.value;
    }
    loginForm.addEventListener("submit", onsubmit);
---
### setInterval
+ 기능 : n ms 간격으로 동작을 반복하여 실행하도록 한다
+ ex
    ``` js
    setInterval(function, n); //첫 번째 인자로는 실행하고자 하는 function을 두 번째 인자로는 대기 시간을 입력한다
    ```
### setTimeout
+ 기능 : n ms 뒤에 동작을 실행시킨다
+ ex
    ``` js
    setTimeout(function, n); //첫 번째 인자로는 실행하고자 하는 function을 두 번째 인자로는 대기 시간을 입력한다
    ```
---
### padStart
+ 기능 : string의 최소 길이를 설정한다
+ ex
    ```js
    "1".padStart(n, "i"); //string의 길이가 n이 되지 않으면 앞에 i를 추가한다
    // ->>> 01
    ```
---
---
## math 함수
### random
+ 기능 : 0부터 1까지의 숫자를 랜덤으로 제공해준다
+ ex
    ```js
    Math.random(); //0부터 10까지의 수를 얻으려면 당연하게도 10을 곱하면 된다
    ```
---
### round
+ 기능 : 소숫점을 반올림 해준다
+ ex
    ```js
    Math.round(1.1); //이건 1이 된다
    Math.round(1.5); //이건 2가 된다
    ```
---
### ceil
+ 기능 : 소숫점을 올림 해준다
+ ex
    ```js
    Math.ceil(1.1); //이건 2가 된다
    ```
---
### floor
+ 기능 : 소숫점을 내림 해준다
+ ex
    ```js
    Math.ceil(1.1); //이건 1이 된다
    ```
---
---
### creatElement
+ 기능 : html에 element를 추가해준다
+ ex
    ```js
    const value = document.createElement("img");
    ```
---
### appendChild
+ 기능 : html을 추가해준다
+ ex
    ```js
    document.body.appendChild(value);
    ```
---
### stringify
+ 기능 : 어떤 것이든 string으로 바꿔준다
+ ex
    ```js
    JSON.stringfy(vlaue);
    ```
---
### parse
+ 기능 : string을 array로 바꿔준다
+ ex    
    ``` js
    JSON.parse("[1,2,3,4]"); // -> [1,2,3,4]
    ```
---
### forEach
+ 기능 : array에 있는 각각의 item에 대해 function을 실행 시켜준다
+ ex 
    ``` js
    valuealbe.forEach();
    ```
---
### Date.now
+ 기능 : 밀리초(1000분의 1초)를 준다    
    + id를 저장하는데에 쓸 수 있다
+ ex 
    ```js
    Date.now();
    ```
---
### filter
+ 기능 : 배열의 값을 함수에 넣어서 불러주고 새 array에 포함될지 결정한다
+ ex
    ```js
    [1,2,3,4].filter(function); // filter함수는 인자로 받은 함수에 배열의 값을 하나씩 넣어서 보내준다
    // 그리고 return값에 따라 item이 새 array에 포함될지  결정한다(true -> 포함, false -> 제외)
    //위 경우에는 function(1), function(2), function(3), function(4)처럼 되는 것이다
    ```
+ ex2
    ```js
    const arr = ["pizza", "apple", "orange"];
    function foodFilter(fruit)
    {
        return fruit !== "pizza"
    }
    arr.filer(foodFilter);
    //이 것의 결과는 ["apple", "orange"] 가 된다
    // 배열의 값들을 하나씩 함수에 보냈을때 flase가 리턴되는건 pizza밖에 없기 때문이다
    ```
---
### getCurrentPosition
+ 기능 : 브라우저에서 위치 좌표를 준다
+ ex
    ``` js
    function onGeoSuc(position)
    {

    }
    function onGeoError()
    {

    }
    navigator.geolocation.getCurrentPosition(onGeoSuc, onGeoError); //getCurrentPosition은 2개의 인자를 가진다.
    //하나는 잘 실행 되었을때의 function이고 다른 하나는 오류가 났을때의 function이다
    //잘 실행이 되었다면 유저의 위치를 매개변수로 넘겨준다
    ```
---
### fetch
+ 기능 : JS가 URL을 대신 불러준다
+ ex
    ```js
    fetch(URL); //fetch는 첫 번째 인자로 url을 받고 두 번째 인자로 옵션을 받는다
    ```
---
## path
### beginPath
+ 기능 : Path를 만든다
+ ex
    ```js
    context.beginPath();
    ```
### moveTo
+ 기능 : x,y 좌표로 옮긴다
+ ex
    ```js
    context.moveTo(x,y);
    ```
### lineTo
+ 기능 : sub-path의 마지막 점을 특정 좌표와 직선으로 연결한다
+ ex
    ```js
    context.lineTo(x,y);
    ```
### stroke
+ 기능 : 현재의 fill style로 현재의 sub-path를 채운다
+ ex
    ```js
    context.stroke();
    ```
---
### fillRect
+ 기능 : 색이 채워진 사각형을 그린다
+ ex
    ```js
    fillRect(x,y,width,height);
    ```
---
### toDataURL
+ 기능 : 지정된 포맷의 이미지 표현을 포함한 data URL을 반환함
+ ex
    ```js
    CanvasElement.toDataURL("image/jpeg");
    ```
---
### map
+ 기능 : 하나의 array에 있는 item들을 바꿔준다
+ ex
    ```js
    ['array'].map(() => "newItem");
    ```
---
### toUpperCase
+ 기능 : 대문자로 바꿔준다
+ ex
    ```js
    const small = 'small';
    small.toUpperCase();
    ```
---