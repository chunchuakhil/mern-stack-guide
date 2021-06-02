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
			
## Back end
