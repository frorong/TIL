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