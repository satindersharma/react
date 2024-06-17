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
