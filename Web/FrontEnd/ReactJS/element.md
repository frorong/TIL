# element

엘리먼트는 리액트 앱의 가장 작은 단위이다  
또한 화면에 표시할 내용을 기술한다

## element 렌더링

react element를 렌더링 하기 위해서는 DOM element를 `ReactDOM.createRoot()`에 전달한 다음  
React element를 `root.render()`에 전달해야 한다

## Update

React DOM은 해당되는 element와 그 자식 element를 이전의 element와 비교하고  
DOM을 원하는 상태로 만드는데 필요한 경우에만 DOM을 Update 한다
