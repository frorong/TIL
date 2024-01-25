**\[Next\] Next.js는 어떻게 SSR과 CSR을 혼합했을까? Next.js의 Hydration**

우리가 코드를 작성하여 만들어진 웹 어플리케이션은 브라우저 위에서 구동된다. 브라우저의 페이지 렌더링 방식은 크게 두 가지가 있는데 바로 CSR(client side rendering)과 SSR(server side rendering)이다.

CSR과 SSR에 대해 궁금하다면 아래 게시글을 참고하자.

[frorong.tistory.com](https://frorong.tistory.com/entry/SSR-%EA%B0%9C%EB%85%90-%EB%B0%94%EB%A1%9C%EC%9E%A1%EA%B8%B0-Server-Side-Rendering)

CSR은 일반적인 SPA 프레임워크를 사용하면 된다.

SSR을 쉽고 효과적으로 사용하기 위해선 Next.js를 채택하는 것이 좋다. 왜 그럴까?

SSR과 CSR은 각각의 장단점이 있다.

예를 들면 SSR은 서버에서 페이지를 렌더링하여렌더링 하여 전달하기 때문에 사용자가 페이지 정보를 빠르게 볼 수 있지만, 페이지 이동 시 새롭게 서버에서 페이지를 렌더링 하여 페이지 이동 속도가 느리다.

반면에 CSR은 페이지 이동 속도는 빠르지만, 페이지가 로딩 된 후 JS가 실행되기 때문에 완전한 페이지를 보기까지는 시간이 좀 걸릴 수 있다.

각 렌더링 방식의 장단점을 모두 고려하여 지원하는 것이 바로 Next.js이다.

Next는 초기 렌더링은 SSR을 지원하여 내용이 채워진 html을 빠르게 가져오고, 이후 라우팅은 CSR방식을 사용한다. 따라서 SEO최적화와 함께 페이지 깜빡임 없는 라우팅을 지원한다.

각 렌더링 방식을 적절히 혼합한 프레임워크인 것이다.

그런데..? SSR을 지원하면서 CSR까지 지원하는 것이 어떻게 가능할까?

Next는 node.js 기반의 서버에서 동작한다.

1\. 먼저, 프론트엔드 환경을 제공해 주는 Next 서버가 클라이언트 요청을 대기하고 있는다.

2\. 요청이 들어오면 첫 페이지를 SSR하여 생성한 pre-rendered HTML과 해당 페이지에 필요한 번들을 클라이언트에 전송한다.

3\. 브라우저는 받은 html로 초기 페이지를 렌더링 한다. 이 시점에서는 JS가 로드되기 전이기 때문에 상호작용은 불가능하다.

4\. JS가 로드되며 상호작용을 위해 hydration을 수행한다. 여기 이 hydration이 중요하다. 좀 더 자세히 알아볼 것이다.

5\. 최초 페이지 로딩 이후 유저가 페이지 이동을 하면 CSR 방식으로 페이지를 처리한다.

이제 Next에서 페이지를 렌더링하는 순서는 알겠는데, hydration이 무엇인지 잘 모르겠다..

## Hydration

hydration은 SSR된 html에 상호작용이 가능하도록 JS를 적용하는 과정을 의미한다.

일반적으로 CSR에서는 html과 JS가 별도로 관리된다. 하지만 SSR에서는 초기 렌더링을 서버에서 수행하고 클라이언트에 전달하기 때문에 이후 클라이언트에서 JS를 적용하는 과정이 필요하다. 서버에서 SSR 된 html에 있는 초기 state나 event handler 등을 JS로 적용하며 동적으로 상호작용 가능한 페이지를 만들어나간다.

Next.js는 이렇게 SSR과 CSR을 적절히 사용한다. 뿐만 아니라 더 다양한 장점들이 있는데, Next의 장단점을 함께 알아보자.

## Next.js의 장단점

**장점**

1\. 앞서 계속 언급했던 장점으로, SSR과 CSR을 적절히 혼용하여 사용자 경험을 향상시킬 수 있다.

2\. 내장된 강력한 라이팅 시스템으로 직관적이고 편리하게 라우팅이 가능하다.

3\. SSR을 지원하기 때문에 따라오는 효과로 SEO 최적화가 있다.

4\. minifying과 code split을 자동으로 지원한다. (아래 게시글 참고)

[frorong.tistory.com](https://frorong.tistory.com/entry/React-%EC%9B%B9-%EA%B0%9C%EB%B0%9C%EC%97%90%EC%84%9C-%EC%84%B1%EB%8A%A5-%EC%B5%9C%EC%A0%81%ED%99%94%ED%95%98%EA%B8%B0-Minifying%EA%B3%BC-Code-Splitting)

5\. React v18의 서버컴포넌트를 지원한다. (아래 게시글 참고)

[frorong.tistory.com](https://frorong.tistory.com/entry/RSC-%EA%B0%9C%EB%85%90-%EB%B0%94%EB%A1%9C%EC%9E%A1%EA%B8%B0-RSC%EC%99%80-css-in-js-React-Server-Component)

**단점**

1\. code split과 같은 최적화 작업 때문에 빌드 시간의 증가가 생길 수 있다.

2\. SSR이 서버에 부하를 일으킬 수 있다.

높은 러닝커브도 단점으로 언급하는 분들이 몇 계시던데 나는 react를 알고있다면 굉장히 쉽게 익힐 수 있어 오히려 러닝커브가 낮다고 생각한다.

## Next.js v14.1

블로그를 작성 중인 이 시점에 Next.js가 14.1 버전으로 업데이트 되었다. 간략하게 변경사항들을 알아보자!

1\. 캐시 제공이 안정화 됨으로써 셀프 호스팅이 향상되었다.

2\. turbo pack이 성능적으로 개선되었다.

3\. 오류 메시지가 보다 명확해졌다.

4\. app router에서 window.history.pushState와 window.history.replaceState 메서드 사용이 허가되었다. 이 메서드들은 페이지를 리로드 하지 않고 history stack을 업데이트할 수 있다.

5\. Next 어플리케이션의 캐시 된 데이터를 관찰하기 위한 로깅 구성 옵션이 업데이트되었다.

6\. getImageProps로 Image 태그를 사용하지 않고도 더 유연한 이미지 처리가 가능해졌다.

## 마치며

오늘은 이렇게 Next에서의 SSR, CSR과 장단점에 대해 알아보았다. 정말 나는 Next.js 만한 프레임워크가 없다고 생각한다. 적어도 내 우물 안에서는 말이다.
