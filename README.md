### What is react

React is javascript library, which work on the diffing algoritm, it is compnonent based architecture
which allow to reuse of code



### what is React Dom


ReactDom is layer above the javascript DOM, it allow to glow react with the DOM. it provide the DOM specific method to the top level of react



### What is JSX

Jsx stand for sytanx extension to javascript, it allows in react to right markup language, its not neccessay to right 
jsx code but it easy to write this type of sytax, it allow to write event driven



### what is Props and state

Props know as property and can be pass one component to other, where state are based to a component and can be pass
to another component as a props


Props are imutable 
State are mutable



props are read-only


state can be modified


state changes asyncronous


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
