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
    