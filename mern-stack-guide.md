# Mern-stack-guide
personal guide and complete reference for mern-stack
## JavaScript
###### what ever you are seeing and entering on the JavaScript based apps is of type only string, the rest is taken care by JavaScript
## es6 features



## Front end
Front end

- initial starter guide.
- don'ts => don't install react things globally, because versions may vary from project to project.
- first install node js latest version
- npx create-react-app my-app 
  - npx a tool comes with node
  - functional component 
  	- import React from 'react';
  		- importing React to the functional component help babel compiler to convert jsx into react Element
  		- The lastest version of react dont require import react inside functional component, automatically it will happen in background
  - React.StrictMode
  	- StrictMode will render the components twice only on the development mode not production.
  	- StrictMode renders components twice in order to detect any problems with your code and warn you about them.
  	- The getDerivedStateFromProps method will call twice.
  - ReactDOM.render
  	- import React => creates html element
  	- import ReactDOM.render => helps render html elements on browser
  - functional component vs class component
  	- a functional component has no state, no lifecycle methods and it’s easy to write(plain function)
  	- a class component has state, lifecycle methods and React creates an instance of a class component every time React renders it.
  	- functional component => just return jsx to and render based on the props, we cant do side Effects like api calls.
  	- class component => returns with render function, because we can call render multiple times, we have react component life cycle methods to do something before render, and after render. ex: we can make a api just before the render happens, so that our data well be ready to display on the screen.
  - if your are using React, dont touch the real DOM. React will handle every thing for you. If you still use it: your dom manipulation and react dom manipulation may collide and lead to errors.

  ### state
  - Dont change the state directly, use react internal methods to update/change the state. If you change/mutate the state directly, react dont update to the real dom, if you use react methods : it will compare the state with virtual dom and update it to the real DOM.
  ### from handling in react
  - https://github.com/jquense/yup
  - https://formik.org/docs/overview

### Redux
- React=>Actions=>Reducers=>Store=>React-View
- Redux store is immutable/notChangable, reducer don't change the store but gives you a new Store.
- Actions
	- on click button send an action to reducer.=> reducer will read it
	- action contains {type:"",payload:""}
	- actions are like plane javaScript object
	- actions are like love letters : which has love type and main naughty matter/payload.
	- its like a action letter passed by collector=> which letter type and letter content/payload
- Reducers
	- are pure functions, it takes (state, action)
	- reducer is like police, which has to access to people and letter passed by collector.
	- Reducer never changes the state, instead they will create new state object, because if you change the store state directly how do you know what is the different between current sate and previous state, to debug the redux store with past and current values , you need to create a new state every time.
- Pure Functions
	- Doesnt have side effects (api calls), Reducers dont have api calls.
	- Doesnt modify its arguments
- Store
	- Store is like a place, which has a reducers.
	- Store is like a gold treasure, if you need to do anything only possible through Reducer/Police person.
	- it has three methods
		- store.getState()
		- store.dispatch()
		- store.subscribe()
	- extra
		- Redux.combineReducers()
		- Redux.applyMiddleware()
- connect function in react-redux
  - connect function returns store as first argument
  - connect function returns dispatch as second argument
  - connect it self is a function which has store and dispatch as a variables and now, connect function takes our component and runs: so that our component will get props from the store.
  - mapStateToProps
  	- Takes store and returns object which has store data.
  	- mapStateToProps gets state from connect function
  - mapDispatchToProps
    - Takes dispatch and returns object which dispatches an action

    - mapDispatchToProps gets dispatch from connect function

- Redux-logger
	- acts as a middleware for redux applications.

#### How to set up react - redux

- create all your action constants, what are the action to be performed be a simple feature. ex... ADD_TASK
- create all your action creators, a simple function which returns object{type, payload}. ex... addTaskAction(task){return {type, payload}}
- create a reducer for your new feature which has new state, use switch case for all your actions. Always create a new object and return a new state object, it will help for state debugging.
- now create store, (if you are using for first time), create store with rootReducer=>which combines all reducers. combineReducer will expect key and value as a function (basically an equivalent reducer function)
- now connect Redux store to our app, mostly use Provider as HigerOrderComponent , so that every child component has store methods access.

###### Components which are connected to Redux are called container components

###### Components which are not connected to Redux are called Presentational Components

​				

### Redux - Saga

##### 	pre requi for redux - saga		

- ​	es5
  - setInterval has (handlerFunction, timeInterval)
  - setTimeout 
- axios
    - axios always returns a promise, we no need to create a promise for api calls
- every function in redux-saga will return will return a generator

#### Redux - Saga 

​	if you are not able to predict whats happening in sideeffects like api calls use redux-saga

##### 		what redux saga can do...?

1. managing sideeffects easiser and managable

2. it is capable of listening to actions that are dispatched

3. and it is capable of dispatching action by its own.

4. It should be middle ware

   #### Types of saga

   1. Watcher saga=>watches for action dispatches, would assign a worker saga for the action
   2. Worker saga=>would do work, get the response from api, and dispatch an action
   3. Root saga=>combines all sagas,

   ##### Effects in saga

   1. takeEvery()=>listens to the actions
   2. call()=>calls an api (promise-based)
   3. put()=> Dispatch an action
   4. all()=>compose all sagas

#### How to set up redux - saga

​		step 1=>first add saga middleware to the redux-middleware, with rootSaga and run the saga.

​		step 2=>create a watcherSaga

```javascript
function* watchDeleteTask(){
  yield takeEvery(DELETE_TASK,deleteTaskWorker)
}
```

​		step 3=>create a workerSaga

```javascript
function* deleteTaskWorker(data){
  yield call(deleteTaskAPI,data.payload)
  yield put(taskDeletedAction(data.payload))
}
```

​			inside call function dont pass data to api // example: yield call(deleteTaskApi(id))

​			its better to pass data as a next argument //example: yield call(deleteTask, id)

​		setp 4=>it is all recommended to use try-catch inside worker-saga, because workers are having some exception on some day.

​		step 5=>combine all watchSagafunctions inside "all"

#### side effects

1. javaScript fetch
2. javaScript promice
3. axios .then .catch
4. redux-thunk
5. redux-saga

### react - router - dom

react-router is parent

install react-router-dom for browser based apps

install react-touter-native for react navive

### Testing

Unit Testing

##### Just 

can be used in with all liberary like react, angular, vue, js

1. describe() - group of test cases (or) test suite
2. it() - test case
3. expect() - assertion function
4. beforeEach()
5. afterEach()
6. beforeAll()
7. afterAll()

##### Enzyme => has concepts

Enzyme only for reactJS

1. deep Rendering- mounting- mount()=====> current component and its child component
2. shallow Rendering- shallow()====> current component only, no children







## Back end
