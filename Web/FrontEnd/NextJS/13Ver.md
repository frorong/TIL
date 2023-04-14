# NextJS 13 version

NextJS 13 version에서는 app directory가 추가되었다.

app directory에서는 기존의 파일로 라우팅이 되는 형태가 아닌 폴더로 라우팅이 된다.

ex

- main/index.js -> /main
- about/index.js -> /about

app directory에서는 layout.js와 page.js가 사용된다.

- layout.js : layout.js 파일은 라우팅을 담당한다.
- page.js : page.js는 기존의 index.js와 비슷한 기능을 한다.

또한 13version의 NextJS는 기본적으로 Server Side Rendering을 지원한다.  
Server side rendering에서는 React함수와 같은 기능을 사용할 수 없다.  
만약 사용하고 싶다면 "use client"라고 명시 해주어야 한다.  
하지만 client side rendering에서는 Metadata를 지원하지 않는다.  
신규 버전이라 불안정한 부분이 많아 보인다.
