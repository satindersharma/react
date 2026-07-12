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

