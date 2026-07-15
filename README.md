# react




`npx create-react-app blog`
`cd blog`
`npm start`

`package.json` contailns our project dependencies
`package-lock.json` contains the detail tree structure of dependencies of dependies



## React with Typescript

###### https://reactjs.org/docs/static-type-checking.html

##### `npx create-react-app your_app_name --template typescript`

## React Functional component

#### export default function
# `rcf`

# `rfce`





### Controlled component

a controlled compnent don't have its local state. it recieve all the data via a props and raises events whenever datais changed. sho this compenent is entirly contolled by its parent


# Stateless functional component
A simple functinal compnent wihtout any local state is a stateless Funtional compenent . A Simple compnent with a return of jsx

# Lifecyle  Hooks

1. Mount. this is when an instance of the compnent is created and inserteded into the dom. at mounting phase we have 3 lifecycle hooks contructor, render, componentDidMount . react will call this method inorder
2. Update. this the 2nd lifecyle phase. this happen when the state or the props of the component get change. at update phase we have 2 ligeclcle hooks render, componentDidUpdate. react will call this method in order
3. Unmount. this is the 3rd and last lifecucle phase. this is when the compent is removed from the dom. componentWillUnmount

constructor: perfect place to set the this.state to this.props
you cant call this.setState in construct as it is available only after coponent is rendered. remember all its childer react lement are rendered recursivelly
componentDidMount perfect pace to get the data from server(like ajax call)

compnentDidUpdate: here when the component is updated this will trigrer. it is a good palce to make any ajax req if the data/ state is changed. so if the previous and curent state is same so no need to make ajax call. this is an optimisation tecqniue


componentWillUnmount called befrore removing copnent from the dom. this will help to cleanup so there iwl be no memory leaks


<br />

***

## why react

browser were ne intend for dom opereation. the whole purpose was to show the documents. dom operation is a costly opereation. browser is written in c++. we code website in js. c++ is fast language js is slow. js not able to intract with ardware. js engige trires to convert the s code in such a way so that the c++ understand

eg. document. getelementbyid this is not js code this is a browser code to tell the c++ code to get the element. when yo do eleent.s.tyle.color  = 'red' then this is given to c++ to to the changes.

in c ther eare CGRect(0 DrawRect() this methods used to draw on your browser screen.

usnif js it directly update dom. where in react it ceheck wheather the update is required or not.

react tries to solve the problem by ninimizing the number of dom updates

you can chek go to inspect ➔ go to Layers tab,  click on any of that 3d rectangles no you can see

### What is react

<br />

### What is babel

```HTML
<html>
  <head>
    <script src='react.js'></script>
    <script src='react-dom.js'></script>
    <script src='bable.js'></script>
  </head>
  <body>
  <div id="root"></div>
    <script type='text/babel'>
      function MyApp() {
        return <h1>Hello, world</h1>
        
      }
      const container = document.getElementById('root')
      const root = ReactDOM.createRoot(container)
      // now you can see this in your browser
      root.render(<MyApp />)
      
    </script>
    
  </body>
</html>
```

babale is a transpiler. browser run by antoehr comany js run by another comapny . now here comes babel. no issue. let new thing came. I will make it capatialbe. take new trendy code as inupt. output as old code so that browser can understand

jsx build by react team so to make react easy. but browser don't understand so they asked bable to write a code to make it understandable by browser

#### JSX

Javascript XML. it is a Syntax extension. we can extent a js file in jsx. we can do all think in jsx that we can do in js

we cannot return multiple value in jsx because when it get converted to normal js it get converted to a function call. in js we cannot return multiple value. to return multiple values make it array or make a object(eg. fragments) 

atributs are camel case . class is className. aria atributes are like aria-label (with dashes)

the tages show be alway have colsing tag. in html \<img /> \<hr/> but in jsx

we canot write staemen insde jsx return

so that we can write the UI  and logic together

xss atach prevention like in js \<img src='0' onerror'alert(1)' />

<br />

### &#x20;VDOM

<br />

react read the dom and make a object reprsentaion vdom  and make a copy of original vdom. now before updateing it first make changes to the copy of vdom and tehn compare it with the origina vdom and check if  changes required then update accodingly

eg. when we do \<Header /> then react create the object of the component

### JSX to UI Journey

Assume an comonent \<Search/>. whenever you call \<Search /> the the compnent object created again and again . by using this object react create a fibernode. Component object genereated again and again when you call Component like this\<Search/>. but the Fibernode check what is changesg. if nothing changeing then the fiibernode do nothing. if anything change fibenode goes to reactDOM. React has lifecycle, managing componenet and creating fibernode whereas Reactdom has the diffeng alg, ui changes ect

we can write extpretion that return a value. we cannt write statement in jsx. also jsx look for first letter to distingush between Component and tag

props are simply arguments passed to component.

#### ESM brings export default fnName.  make \<script type='module' src='app.js'>

it was indrduced in es6. it is a module system

```JavaScript
 // app2.js
function geData() {
  console.log('from module')
}

export default getData;
```

```HTML
<!-- index.html -->
<!DOCTYPE html>
<html>
  <body>
    <script type='module' scr='app2.js'></script>
    <script type='module'>
      import getData form './app2.js';
      getData();
    </script>
  </body>
</html>
```

WebPack: package bundlers

cobine all file sand make a file like single main.js in build.static/js

npx is to run a comand, npm is to install a package

loaders tells the webpack to how to treat diff ts or css files

Entry ➔ Loaders ➔ Bundling ➔ plugins ➔ output

CRA was old way to create react project

Vite is new. no js file combination. as now module system is available in all bowrser. so it wll will break the js in two category. one is thta is not changeing. i.e nodemode. so vite make buid of those at one time. then what we change in our code then vite build that again in agian which make it fater then webpack. esbuild

useRef ➔ react way of doing document.getElementById

useState➔ 

rerender means again and again function call. its not about the ui update again and again. if you don't have heavy calculation then no need to take tensio about  rerender

react updates in batch but it was not in before versions. in react 18 we have the updates of the states in the batch

<br />

<br />

Rerender means calling your component again with updated values

```JSX
const [c, setC] = useStae(0)

setC(c+1) // this will now used
setC(c+1) // 
setC(c+1)

//  take the snapshot values as they are prossing in batch
// if you pass a function in the setter like this
setC((prev) => prev + 1)
setC((prev) => prev + 1)
setC((prev) => prev + 1)
// wen we use a callback funtion then the react use the reutrn value, now this new value will be pased to next call back function ,
// there for we get new value
setC(9)  // this is the replacement value
setC(()=>{}) // this will use replacement value


```

##### setC(c+1) // setter function always pic state from the initial render

| Initital | Que       | Return Value |
| :------- | :-------- | :----------- |
| 0        | setC(c+1) | discart      |
| <br />   | setC(c+1) | discart      |
| <br />   | setC(c+1) | discart      |

##### with callback like this setC((prev) => prev + 1) .this will use return value

| initial | Que                      | Return Value |
| :------ | :----------------------- | :----------- |
| 0       | setC((prev) => prev + 1) | 1            |
| <br />  | setC((prev) => prev + 1) | 2            |
| <br />  | setC((prev) => prev + 1) | 3            |

### LIfecycle

```JSX
function Person() {
  return <h1>person</h1>
}

<Person /> // => this is same like new Person() => react.createElement cals me
// this will make it like a object
const obj = {
  type: h1, 
  value: person
}
// this will compare with the original object. it anything change then this will update on UI

// this will mount the component


//  react incourage you to now not see the functional component in the as lifecycle. look it like Synchoroniztion 


// useEffect


useEffect(()=>{
  console.log('Component Mounted.') // this will sheduled
  return function () {
    // cleanup funtion
    console.log('unmouning ')
  }
}, [])

// return will run and after the ui is shown then useEffect will run

  // also if you have nested elements/ component, then the child will render first
// how to unmount 
  // using conditinal rendring


```

return will run and after the UI is shown then useEffect will run

also if you have nested elements/ component, then the child will render first

how to unmount

using conditional rendring ( remember react will work condition rendering only on Boolean value. for react 0 is a valid value. it will render.

on unmount first parent cleanup function will run then child and then its inner child

<br />

Stress testing. I f you run the react. at first it will do the stress testing means React Mounts and Remout Your Components. to check if you have properly implemented the useeffect cleanup 

### \<React.StrictMode>. in this react will do these 3 thinks

```JSX
<React.StrictMode>
  <App/>
</React.StrictMode>
```

1. Re-Render Your Application
2. useEffects  will call 2 times, first mounts then unmount and then mount
3. if you are usign any outdated lib then react will show Depricated Warning /Errors

Sometimes you need to run the useEffects only one time. 

```JSX
import './App.css'
import {useState, useEffect} from 'react'

let isFirstlaunch = true; // as this is outside of the functinop/Component so it is outside of the rerender cycle. 
// that is why this will intiate once and will available with updated value after every component render/rerender
 
function App(){
  const [count, setCount] = useState(0);
  useEffect(()=>{
    console.log('Component Mounted'); //shedule
    if(isFirstlaunch){ // do this if you are looking to call only once
      isFirstlaunch = false;
    showData(); // now this will call only once
    }
    return function(){
      isFirstlaunch = false;
      //  if you have any api call so make this flag false in your cleanup function also .
      //  so that if api data will come in a delay then no action will perform
      console.log('unmount')
      
    }
  },[]);

  function showData(){
    console.log('getData')
  }
}
```

```JSX
// other way to only call api once
// by using AbortConrtoller


import './App.css'
import {useState, useEffect} from 'react'

function App(){
  const [count, setCount] = useState(0);
  useEffect(()=>{
    console.log('Component Mounted');
    const controller = new AbortController();
    const signal = controller.signal
    fetch('apc', {signal:signal}).then()
    showData(); // now this will call only once
    }
    return function(){
      controller.abort(); // you will se the 2 requirest in network tab but this will abort the first reqest.
      console.log('unmount')
      
    }
  },[]);


}
```

There is no lifecycle methods in react functional component. useeffect we used to syncronise your component with external data

```JSX
// pure function / same output for same input and not acceing outside variable or reference
let x = 9
function sum(a) {
  return a + x // this is not a pure function
}

console.log(sum(2))
console.log(sum(2))

function sum(a) {
  return 0 + x // this is a pure function
}

console.log(sum(2))
console.log(sum(2))

// is console.log is not pure function. as it is accing outside 
console.log(x)// this is accing x

function sum() {
  // this is a pure function
}

console.log(sum(2))
console.log(sum(2))

function sum(a, b) {
  return a + b // this is a pure function
}

console.log(sum(2,3))
console.log(sum(2,3))

function sum(a, b) {
  return a + b + 2 // this is a pure function
}

function sum(a, b) {
  return a + b + 2 + x  // this is not a pure function
  // because it is accessign a variable that is not in its own scope
}

// pure function make it more debugable or testable,
// so everyone should try to write a pure function

```

UseEfffect ➔ what is effect anything that accing outside the react world. we use the useeffect when we are going to communicate with outside the react world. axios, fetch call, evenlistner, localstorage, browserapi socket connection

useeffect will call in the same order how you are written in file

##### 3 flavours of ueEffect

```JSX
// 3 flavours of ueEffect
useEffect(()=>{}})
// call this effect on every state change
// syncronize my component from outside world on every state change

useEffect(()=>{}}, [])
// call this effect once, when my component Mounts
// syncronize my component from outside world  when my component Mounts

useEffect(()=>{}}, [someVariable])
// call this effect once, when my component Mounts and 
// whenever the reactive variable passed in dependcy array changes

// syncronize my component from outside world  when my component Mounts and 
// whenever the reactive variable passed in dependcy array changes

// warning

// the below one is dangrous when we have some state change in it like this
useEffect(()=>{
  setState(); / will cause an infinite loop
}})


// also cleanup will call on unmount and  if thre is any dependency reactive variable, then it will be called on change/update of reactive varable
```

<br />

```CSS
/* // /component/my-component/style.css */
.your-component{
  
}
```

```JavaScript
// /component/my-component/utils.js

// if a funtion is only related to compeoonent then add over here otherwise  src/utils
export function getData(){
  
}
```

```JavaScript
// /component/my-component/constant.js
export DEFAULT_AGE = 18;
```

```JSX
// file structure
// /component/my-component/index.js

import React from 'react'; //first should be the third party libratires
import React from 'react'; //first should be the third party libratires
import React from 'react'; //first should be the third party libratires
// a gap
import {getData} from './utils'; // then your function

const {DEFAULT_AGE} from './constant'; // your constant

import './style.css' // then your styles


function YourComponent(props) {
  const {} = props; // first line props destructure

  // redux data

  // useState call

  // custom hooks call

  // useeffects. all useeffects at one place

  // yours functions

  // variables drived from state. eg
  const message = `${score} hello ` 

  

  
  return <div className='your-component'></div>
}

```

useEffect and useState

