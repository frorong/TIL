# Tips
### input
+ input을 필수 입력 항목으로 만드려면?
    + required를 사용
    + ex
    ``` html
    <input required>
    ```
+ input의 최대 길이를 정하려면?
    + maxlength를 사용
     + ex
    ``` html
    <input maxlenght="15">
    ```
---
###
### Tag
+ tag + class, id 동시에 적기
    + ex
        ```html
        div.classname 엔터 -> <div class="classname"></div>
        a#idid 엔터 -> <a id="idid"></a>
        p.classname#idid 엔터 -> <p class="classname" id="idid"></p>
        ```
    + 활용
        ```html
        div.classname>button#button1+button#button2 엔터 ->
        <div class="classname">
            <button id="button1"></button>
            <button id="button2"></button>
        </div>
        ```
        이 것을 보고 굉장히 놀랐었다
+ 한번에 여러개의 태그 만들기
    + ex
        ```html
        div.classname*3 엔터 -> 
        <div class="classname"></div>
        <div class="classname"></div>
        <div class="classname"></div>
        ```
---