# React Hooks

+ functional component에서 state를 가질 수 있게 해준다

## 1. Use State
+ useState는 2개의 value를 return한다, 상태를 관리해준다
+ ``` js
    import React, { useState } from "react";

    const [key, setKey] = useState(default);
    ```

### 2. Use Input
+ useInput은 input을 업데이트 한다
+ ``` js
    const useInput = (initialValue, validator) => {
        const [value, setValue] = useState(initialValue);
        const onChange = event => {
            const {
                target: {value}
            } = event;
            let willUpdate = true;
            if(willUpdate){
                setValue(value);
            }
            if(typeof validator === "function"){
                 willUpdate = validator(value);
            };
        };
        return {value, onChange};
    };
    const App = () => {
        const maxLength = value => value.lenght < 10; //10글자 아래로 적용된다
        const name = useInput("Mr.");
        return(
            <input {...name} />
        )
    }
    ```

### 3. Use Tab
+ [->](https://github.com/Lee-Seungje/React-Hooks/blob/main/useState/useTab.js)

## 4. Use Effect

state를 change할 때 마다 똑같이 function이 다시 실행된다\
=> 가끔 특정 코드의 실행을 제한하고 싶다

useEffect는 2개의 인자를 가지는 함수이다  
우리 코드가 딱 한번만 실행될 수 있도록 보호해준다
+ 첫 번째 인자는 우리가 딱 한번만 실행하고 싶은 코드이다  
+ 두 번째 인자는 변화를 지켜볼 dependency인데 변화가 생기면 첫 번째 인자인 코드가 실행된다  
두 번째 인자를 [ ]로 비워둔다면 처음 한 번만 실행된다
```js
const [value, setValue] = useState(" ");
useEffect(() => {
    console.log("실행");
}, [value]);
```
위와 같은 경우에는 value가 update될 때 마다 "실행" 이라고 찍힌다

```js
const [value, setValue] = useState(" ");
const [VALUE, SETvALUE] = useState(" ");
useEffect(() => {
    console.log("value와 VALUE가 바뀔 때 실행");
}, [value, VALUE]);
```
위와 같은 경우처럼 두 가지를 동시에 지켜볼 수도 있다

### Use Title

+ 제목을 업데이트 시켜준다
+ ```js
    const useTitle = (initialTitle) => {
    const [title, setTitle] = useState(initialTitle);
    const updateTitle = () => {
        const htmlTitle = document.querySelector("title");
        htmlTitle.innerText = title;
    }
    useEffect(updateTitle,[title])
    return setTitle;
    }

    const App = () => {
    const titleUpdate = useTitle("Loading...");
    };
    ```

#### reference
+ component의 특정 부분을 선택할 수 있는 방법

### Use Click
유저의 클릭을 확인한다
```js
const useClick = (onClick) => {
  const element = useRef();
  useEffect(() => {
    if(element.current){
      element.current.addEventListener("click", onClick);
    }
    return()=>{
      if(element.current){
        element.current.removeEventListener("click", onClick);
      }
    }
  },[]);
  return element;
}

const App = () => {
  const sayHello = () => console.log("say hello");
  const title = useClick();
  return (
    <div className="App">
      <h1 ref={title} >Hi</h1>
    </div>
  );
};
```

### Use Confirm
```js
const useConfirm = (message = "", onConfirm, onCencel) => {
  if (!onConfirm || typeof onConfirm !== "function") {
    return;
  }
  if (onCencel && typeof onConfirm !== "function") {
    return;
  }
  const confirmAction = () => {
    if (window.confirm(message)) {
      onConfirm();
    } else {
      onCencel();
    }
    return confirmAction;
  };
};

const App = () => {
  const deleteWorld = () => {
    console.log("Deleting the world ...");
  };
  const abort = () => {
    console.log("Aborted");
  };
  const confirmDelete = useConfirm("Are you sure", deleteWorld, abort);
  return (
    <div className="App">
      <button onClick={confirmDelete}>Delete the world</button>
    </div>
  );
};
```

### Use PreventLeave
+ 유저가 나갈 때 메세지를 남긴다   
굉장히 좋은듯  
```js
const usePreventLeave = () => {
  const listener = (event) => {
    event.preventDefault();
    event.returnValue = "";
  };
  const enablePrevent = () => window.addEventListener("beforeunload", listener);
  const disablePrevent = () =>
    window.removeEventListener("beforeunload", listener);
  return { enablePrevent, disablePrevent };
};

const App = () => {
  const { enablePrevent, disablePrevent } = usePreventLeave();
  return (
    <div className="App">
      <button onClick={enablePrevent}>Protect</button>
      <button onClick={disablePrevent}>UnProtect</button>
    </div>
  );
};
```


### Use Before Leave
+ 유저의 마우스 포인터가 화면 밖으로 나가면 이벤트가 실행된다
```js
const useBeforeLeave = (onBefore) => {
  if (typeof onBefore !== "function") {
    return;
  }
  const handle = (event) => {
    const { clientY } = event;
    if (clientY <= 0) {
      onBefore();
    }
  };
  useEffect(() => {
    document.addEventListener("mouseleave", handle);
    return () => {
      document.removeEventListener("mouseleave", handle);
    };
  }, []);
};

const App = () => {
  const begForLife = () => {};
  useBeforeLeave(begForLife);
  return (
    <div className="App">
      <h1>Hello</h1>
    </div>
  );
};
```

### Use FadeIn
요소가 천천히 나타나게 한다
```js
const useFadeIn = (duration=1, delay =0) => {
  if(typeof duration != "number" || typeof delay != "number"){
    return;
  }
  const element = useRef();
  useEffect(() => {
    if(element.current){
      const { current} = element;
      current.style.transition = `opacity ${duration}s ease-in-out ${delay}s`
      current.style.opacity = 1;
    }
  },[])
  return {ref : element, style : {opacity:0}};
}

const App = () => {
  const fadeInH1 = useFadeIn(2,2);
  const fadeInP = useFadeIn(5,1);
  return (
    <div className="App">
      <h1 {...fadeInH1}>Hello</h1>
      <p {...fadeInP}>블라블라</p>
    </div>
  );
};
```

### Use Network
유저의 넽워크 연결 상태를 알려준다
```js
const useNetwork = (onChange) => {
  const [status, setStatus] = useState(navigator.onLine);
  const handleCahnge = () => {
    if (typeof onChange === "function") {
      onChange(navigator.onLine);
    }
    setStatus(navigator.onLine);
  };
  useEffect(() => {
    window.addEventListener("online", handleCahnge);
    window.addEventListener("offline", handleCahnge);
    () => {
      window.removeEventListener("online", handleCahnge);
      window.removeEventListener("offline", handleCahnge);
    };
  }, []);
  return status;
};

const App = () => {
  const handleNetworkChange = (online) => {
    console.log(online ? "we just went online" : "we are offline");
  };
  const onLine = useNetwork();
  return (
    <div className="App">
      <h1>{onLine ? "OnLine" : "OffLine"}</h1>
    </div>
  );
};
```

### Use Scroll
유저의 스크롤을 감지해서 이벤트를 준다
```js
const useScroll = () => {
  const [state, setState] = useState({x:0,y:0});
  const onscroll = () => {
    setState({ y : window.scrollY, x : window.scrollX });
  }
  useEffect(() => {
    window.addEventListener("scroll", onscroll);
    return () => window.removeEventListener("scroll", onscroll);  
  },[])
  return state;
}

const App = () => {
  const {y} = useScroll();
  return (
    <div className="App" style={{height: "1000vh" }}>
      <h1 style={{position:"fixed", color:y > 100 ? "red" : "blue" }}>Hello</h1>
    </div>
  );
};
```

### Use FullScreen
겁나 어렵다
```js
const useFullScreen = () => {
  const element = useRef();
  const runCb = (isFull) => {
    if (callback && typeof callback === "function") {
      callback(isFull);
    }
  };
  const triggerFull = () => {
    if (element.current) {
      if (element.current.requestFullscreen) {
        element.current.requestFullscreen();
      } else if (element.current.mozRequestFullScreen) {
        element.current.mozRequestFullScreen();
      } else if (element.current.webkitRequestFullscreen) {
        element.current.webkitRequestFullscreen();
      } else if (element.current.msRequestFullscreen) {
        element.current.msRequestFullscreen();
      }
      runCb(true);
    }
  };
  const exitFull = () => {
    document.exitFullscreen();
    if (callback && typeof callback === "function") {
      callback(false);
    }
  };
  return { element, triggerFull, exitFull };
};

const App = () => {
  const callback = (isFull) => {
    console.log(isFull ? "We are full" : "We are Empty");
  };
  const { element, triggerFull, exitFull } = useFullScreen();
  return (
    <div className="App">
      <div ref={element}>
        <img src="http://www.yonexmall.com/shop/data/skin/standard_C/img/banner/logo.jpg" />
        <button onClick={exitFull}>Make small Screnn</button>
      </div>
      <button onClick={triggerFull}>Make Full Screnn</button>
    </div>
  );
};
```

### Use Notification
알람을 보내준다  
가 다가 아니다  
이건 걍 미쳤다 엄청나다 최고이다
```js
const useNotification = (title, opctions) => {
  if (!("Notification" in window)) {
    return;
  }
  const fireNotification = () => {
    if (Notification.permission !== "granted") {
      Notification.requestPermission().then((permission) => {
        if (permission === "granted") {
          new Notification(title, opctions);
        } else {
          return;
        }
      });
    } else {
      new Notification(title, opctions);
    }
  };
  return fireNotification;
};

const App = () => {
  const tNotification = useNotification("당신은 김경수인가요?", {
    body: "맞다면 moondgod@gmail.com으로 인증을 해주세요 상품을 드립니다"
  });
  return (
    <div className="App">
      <button onClick={tNotification}>절대 누르지 마세요</button>
    </div>
  );
};

```

### Use Axios

Axios
```js
import defaultAxios from "axios";
import { useEffect, useState } from "react";

const useAxios = (opts, axiosInstance = defaultAxios) => {
  const [state, setState] = useState({
    loading: true,
    error: null,
    data: null
  });
  const [trigger, setTrigger] = useState(0);
  if (!opts.url) {
    return;
  }
  const refetch = () => {
    setState;
    ({ ...state, loading: true });
    setTrigger(Date.now());
  };
  useEffect(() => {
    axiosInstance(opts)
      .then((data) => {
        setState({
          ...state,
          loading: false,
          data
        });
      })
      .catch((error) => {
        setState({ ...state, loading: false, error });
      });
  }, [trigger]);
  return { ...state, refetch };
};

export default useAxios;
```

index.js
```js
import React, { useState, useEffect, useRef } from "react";
import ReactDOM from "react-dom";
import useAxios from "./useAxios";

const App = () => {
  const { loading, data, error, refetch } = useAxios({
    url: "https://yts.mx/api/v2/list_movies.json"
  });
  return (
    <div className="App">
      <h1>{data && data.status}</h1>
      <h2>{loading && "Loading"}</h2>
      <button onClick={refetch}>refetch</button>
    </div>
  );
};

const rootElement = document.getElementById("root");
ReactDOM.render(<App />, rootElement);

```