# mern-stack-guide
personal guide and complete reference for mern-stack
## javaScript
### what ever you are seeing and entering on the javascript based apps is of type only string, the rest is taken care by javascript
## es6 features

## Front end
- Front end
 - step 1
    - initial stater guide.
    - donts => dont install react things globally, because versions may vary from project to project.
    - first install node js latest version
    - npx create-react-app my-app 
      - npx a tool comes with node
		- functionl component 
			- import React from 'react';
				- importing React to the functionl component help babel compiler to convert jsx into reactElement
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
			- functional component => just return jsx to and render based on the props, we cant do sideEffects like api calls.
			- class component => returns with render function, because we can call render multiple times, we have react component life cycle methods to do something before render, and after render. ex: we can make a api just before the render happens, so that our data well be ready to display on the screen.
		- if your are using React, dont touch the real DOM. React will handle every thing for you. If you still use it: your dom manipulation and react dom manipulation may colide and lead to errors.

		### state
		- Dont change the state directly, use react internal methods to update/change the state. If you change/mutate the state directly, react dont update to the real dom, if you use react methods : it will compare the state with virtual dom and update it to the real DOM.
		### from handling in react
		- https://github.com/jquense/yup
		- https://formik.org/docs/overview
		### Redux
		- React=>Actions=>Reducers=>Store=>React-View
		- Redux store is immutable/notChangable, reducer dont change the store but gives you a new Store.
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
		### Redux-logger
			- acts as a middleware for redux applications.
			
			
## Back end
