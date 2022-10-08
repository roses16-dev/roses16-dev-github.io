---
layout: single
title: "[react] Input 태그 value 접근하기"
categories: react
toc: true
sidebar:
  nav: "docs"
---

### useState, Ref, Form

### useState

Input 태그 내 입력값이 변할 때 마다 ( onChange ) 해당 값을 setState로 저장하여 사용한다.

```jsx
import { useState } from 'react'

const [name, setname] = useState('');					// useState 변수를 생성한다.

  function onChange(event){								// 매개변수 'event'는 이벤트가 발생한 태그의 정보를 가져온다.
    setname(event.target.value)							// 값이 바뀔때마다 setname으로 name값을 변경해준다.
  }

  return (
      <input type="text" onChange={onChange}></input>	// onChange 이벤트가 발생하면 (input 값이 바뀌면) onChange 함수를 실행한다.
  );
```

위 예제와 같이 사용하면 값이 한글자 한글자 입력되거나, 지워질때마다 변수 `name`의 값도 변경된다. 
`useState`를 사용하여 값이 변경될때마다 re-rendering이 발생하나 성능에 큰 영향을 줄 정도는 아니라고 한다.



### Ref

useRef Hook은 HTML요소에 접근할 때 사용한다.

```jsx
import { useRef, useState } from 'react' 
const [name, setname] = useState('');					
const nameInput = useRef()							// 1. useRef 변수를 생성한다.

  function changeName(){								
    setname(nameInput.current.value)				
    // 3. useRef변수(nameInput).current.value 에 할당된 HTML요소의 value 값을 가지고 있다.
  }

  return (
      <input type="text" ref={nameInput}></input>	// 2. 생성한 useRef 변수를 HTML 할당한다.
      <input type="button" onClick={changeName}></input>
  );
```

같은 방식으로 Text Input 뿐 아니라 다른 HTML 요소에도 사용할 수 있다.



### Form

Form과 Submit 태그를 이용하여 event 정보를 받아와 사용한다.

```jsx
import { useState } from 'react'
function Form(){
    const [name, setname] = useState('');
    
    function addName(event){				// 함수를 실행시킨 Element의 정보를 event로 받아온다. ( 당 예제에서는 Form )
        event.preventDefault()				
		setname(event.target.name.value)	// event.target.아래에서 지정한 name값.value로 text input에 입력된 값을 사용할 수 있다.
    }
    
    return ( <form onSubmit={addName}>				<!-- Submit 버튼을 누르면 addName 함수를 실행한다. -->
                <input type="text" name="name"></input>
                <input type="submit" value="추가"></input>
            </form>)
}
```

- `event.preventDefault() `

  submit은 실행 시 지정한 행동 뿐 아니라 새로운 페이지로 이동하는 HTML의 기본 동작을 포함하고 있다. 위 예제에서도 addName이라는 Function만을 실행하게 되어있으나 페이지 이동까지가 동작에 포함되어있다보니 함수를 실행한 후 새로고침이 된다. 

  `event.preventDefault()	` 메소드는 어떤 이벤트를 명시적으로 처리하지 않은 경우, 해당 이벤트에 대한 사용자 에이전트의 기본동작을 실행하지 않도록 지정한다. 즉, submit의 기본동작인 페이지 이동을 멈춘다.
