### What is react

React is javascript library, which work on the diffing algoritm, it is compnonent based architecture
which allow to reuse of code

### what is Reconciliation ?
React is creating virtual representation of our UI in memory and then ReactDOM receive that and sync with our UI to the DOM. this is Reconciliation.

### what is React Dom


ReactDom is layer above the javascript DOM, it allow to glow react with the DOM. it provide the DOM specific method to the top level of react



### What is JSX

Jsx stand for sytanx extension to javascript, 
Jsx used for special syntax for react that make to represent our UI
Jx looks like HTML but it is not HTML
JSX code get transformed into React.CreateElement
JSX is not part of our browser, so we need babel for converting to valid Javascript


### what is Props and state

Props know as property and can be pass one component to other, where state are based to a component and can be pass
to another component as a props


Props are imutable 
State are mutable



props are read-only


state can be modified


state changes asyncronous

### what is useMemo?
useMemo is use for memozite the return value, its useful when state get update and our entire component get re-render, and in this sitution system will re-calcuate the function, so avoid this heavy compute we use the useMemo
```
useMemo( () => function() {
return 
}, [number] );


```


### what is useCallback?
useCallback memozize the function, so it avoid the re-rendering of function 

```
useCallback ( () => { return myNumber * 5 }, [myNumber]) 
```
### what is useRef ?

useRef useful in 2 sitution ,
 useRef use for avoid re-rendering of the component,
 and also create a reference to the DOM element

### Explain GetDerivedStateFromProps

this lifecycle introduce in react 16, and this replace the lifecycle of componentWillReceiveProps,

its a staic method/lifecycle reason is the want to discourage to make site effect in this lifecycle

this lifecycle should return either null or an object

and changes in the state, this invoke just before the componet mount or update,
so before componentDidMount or ComponentDidupdate


```
static getDerivedStateFromProps(props, state) {
return null;
// or return {
}
}
```

### Define React lifecycle

```

we can break react lifecycle in three phases

1-> Mounting

2-> Updatation

3-> UnMounting


Mounting

1-> constructor(props)

2-> static getDerivedStateFromProps(props, state) 

3-> render

4-> componentDidMount()



Updation

1. GetDerivedStateFromProps

2 shouldComponentUpdate(p, s)



5-> render




4 getSnapShotBeforeUpdate(p,s)


6 ComponentDidUpdate(s, p, snapshot)


Unmount

componentwillUnmount() {


````



### Diff between bind, call , apply




call , and apply --> immediately invoke the function , but in apply we send an array , and call send a comma seprated value


bind --> return a new function

 
Q: What is Context?

Context allows us to avoid prop drilling, so let suppose we have a WareHouse Component, and it send company details to CompanyComponent, and this component only surpass the prop to CompanyName component so it is prop Drilling lets avoid this 

```
 CompanyContext.js
 
 export default CompanyContext = React.createContext('defaultvalue');


WareHouse.js

import CompanyContext ....
const companyObject = {
name: ['1', 2]
}

render() {

return (
 <CompanyContext.Provider value = {companyObject} >
  <CompanyComponent />
 </CompanyContext>
)
}


CompanyComponent.js

//its calling the CompanyName


CompanyName.js

import CompanyContext from '../'

class CompanyName extends React.component {
  static contextType = CompanyContext; // this should be specific
  
  
  render() {
  
  const {name} = this.context;
  
  

}
```
In functional component

```
import CompanyContext 

return () {
 const org = useContext(CompanyContext)
}

```


### explain Forward Refs

forward refs helps in passing ref from parent to child,  we can handle the reference in parent 


##Javascript

### What is Garbage Collector

Javascript is a Garbage collector language and its a process of free up memory by destroy unsed property/object


### what is memory leak ?
piece of memory which no longer being used by application but some reason its never get termined from memory heap.


### what is memory heap and call stack 

Memomy Heap : Where the mormory allocation happen
Call Stack : where code executed


### what is lexical environment 
 first of fall lexical environment and lexical scope are diff things
 so lexical environment means where code is written during execution
 lets take an example
 
 ```
 function a() { }
 
 function b() {
  function c() {}
  }
  ```
  here function a lexical environment is global and function c lexcial env is function b as we
  are seeing where these are written
  
  ### what is lexical scope and dynamic scope ?
  #### dynamic scope: 
   where function is called
 #### lexical scope: 
  aviable variable


### what is IFFE ?
IFFE (Immediately-invoked function expression) is a way to execute functions immediately, as soon as they created
this are useul becuse they don't pollute the global object

### what is execution context ?
whenever code is run is Javascript it run inside the execution context, and it run global execution first from call stack.


### what is Global execution 
during exeution context first thing execute in call stack is global execution 
and it has two property 1. Global object 2. this
also app get hosited (below is hositing)
global object in jS is window


### what is hoisting
hoiting is a behavior of moving function or variable declaration to the top of their respective environment during
the compile time, variable partially hosted and function declaration are hoisted




### what is function declarion and function expression

function declaration --->
```
function a() {}
```
function expression
```
const fu = function() {} 
```

### what is recursion function 
Recursion are those who call them self
```
function a(){
//may be put some Leve event like if else
a();
}

```

### what is Set

Set is special type of Collection in javascipt along with Map, so set are collection of values
without keys, where each value may occur only once


### what the diff between function() * name() and function() name()

function namne() is like a normal function but function* name() indicate it is a generator function
GF are functions that generaated function that can be exited and later re-entered,  an iterator object for for the function itself and each yield or return work as 
return value on each calling time, but you can only one return here
https://jsfiddle.net/Reuben_Rahul/s0y8zvqx/1/
