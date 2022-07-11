# Tips
+ class 이름을 바꿀 때 코드를 깔끔하게 하려면? // JS로 모든 class name을 변경하진 않는다
    + 변수를 선언하여 이름을 지정해주고 변수를 이용하여 이름을 바꾼다
    + 별로인 예시
    ``` JS
    if(h1.className === "clicked")
    {
        h1.className = "";
    }
    else
    {
        h1.className = "clicked";
    }
    ```
    + 나은 예시 
    ``` JS
    const clickedClass = "clicked";
    if(h1.className === clickenClass)
    {
        h1.className = "";
    }
    else
    {
        h1.className = clickenClass;
    }
    ```
    + classList를 이용한 보다 나은 예시
    ```JS
    // classList
    // 기능 : class들의 목록으로 작업할 수 있도록 허용해준다
    const clickenClass = "clicked"
    if(h1.classList.contains(clickenClass))
    {
        h1.classList.remove(clickenClass);
    }
    else    
    {
        h1.classList.add(clickenClass);
    }
+ toggle을 이용한 매우 나은 예시
    ```JS
    h1.classList.toggle("clicked"); //단 한 줄로 해결 가능!!!
    ```
---
+ input의 value를 받아오려면?
    + click eventListener를 이용해 click 이벤트가 발생했을 때 받아오기
        ```JS
        const nameLog = document.querySelector(".form input"); //html의 form class안의 input
        const buttonLog = document.querySelector(".form button"); //html의 form class안의 button
        function clickedButton() //click event시 실행되는 함수
        {
            const valueOfLogin = nameLog.value; //input의 value를 받아온다
            console.log(valueOfLogin); //value 출력
        }
        buttonLog.addEventListener("click", clickedButton); //eventListener
        ```
    + submit event를 감지하여 받아오기
        ```js
        const loginForm = document.querySelector(".form"); //html의 form class
        function onSubmit() //submit event시 실행되는 함수
        {
            const valueOfLogin = nameLog.value; //input의 value를 받아온다
        }
        loginForm.addEventListener("submit", onsubmit); //submit 감지
---
+ string의 길이를 구하려면?
    + .length를 사용한다\
        ex
        ``` JS
        string.length
        ```
---
+ 변수를 string 안에 넣는 2가지 방법
    + 1.
    ``` JS
    "hello " + value;
    ```
    + 2.
    ``` JS
    `hello ${value}`; //``백틱 기호
    ```
---
+ 정보를 저장하려면?
    + localStorage를 사용
        ```JS
        localStroage.setItem("key", value); //값을 저장
        ```
        ```JS
        localStroage.getItem("key"); //값을 회수
        ```
        ```JS
        localStroage.removeItem("key"); //값을 삭제
        ```
---
+ 현재 시각을 알고싶으면?
    + date를 이용
        ``` js
        date.getDate() //날짜를 알려준다
        date.getDay() //요일을 알려준다
        date.getFullYear() //연도를 알려준다
        date.getHours() //시간을 알려준다
        date.getMinutes() //분을 알려준다
        date.getSeconds() //초를 알려준다
        ```
---
+ 시계 만들기
    ```js
    const clock = document.querySelector("h2#clock"); //html에서 id가 clock인 h2를 가져온다
    function getClock()
    {
        const date = new Date(); //날짜를 받아온다
        const hours = String(date.getHours()).padStart(2, "0"); //시간을 받아온다
        const minutes = String(date.getMinutes()).padStart(2, "0"); //분을 받아온다
        const seconds = String(date.getSeconds()).padStart(2, "0"); //초를 받아온다
        clock.innerText = `${hours}:${minutes}:${seconds}` //종합하여 출력한다
    }
    getClock();
    setInterval(getClock, 1000); //1초마다 getClock을 실행시킨다
    ```
---
+ code 간소화
    ```js
    function sayhello(item)
    {
        console.log("this", item);
    }
    parsedToDos.forEach(sayhello);
    // 이것이
    parsedToDos.forEach((item) => console.log("this", item));
    // 이렇게
    ```
---
+ 유저의 위치를 알고싶다면??
    ```js
    function onGeoSuc(position)
    {
        const lat = position.coords.latitude; //위도
        const lng = position.coords.longitude;  //경도
        console.log("you live in" + lat + lng); //console에 위도, 경도 출력
    }
    function onGeoError()
    {
        alert("날씨 정보 없음"); //오류 발생시 경고
    }
    navigator.geolocation.getCurrentPosition(onGeoSuc, onGeoError);
    ```
---
+ 우클릭을 방지하려면??
    ```js
    function(event)
    {
        event.preventDefault();
    }
    .addEventListener("contextmenu", function);
    ```
---