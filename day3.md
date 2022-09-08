## 15. Difference between Axios and fetch.
# Axios :
Axios is a Javascript library used to make HTTP requests from node.js or XMLHttpRequests from the browser and it supports the Promise API that is native to JS ES6. It can be used intercept HTTP requests and responses and enables client-side protection against XSRF. It also has the ability to cancel requests. 
EX::
    axios.get('url')
    .then((response) => {

    	// Code for handling the response
    })
    .catch((error) => {

    	// Code for handling the error
    })

# Fetch: 
The Fetch API provides a fetch() method defined on the window object. It also provides a JavaScript interface for accessing and manipulating parts of the HTTP pipeline (requests and responses). The fetch method has one mandatory argument- the URL of the resource to be fetched. This method returns a Promise that can be used to retrieve the response of the request.
EX::
    fetch('path-to-the-resource-to-be-fetched')
    .then((response) => {

    	// Code for handling the response
    })
    .catch((error) => {

    	// Code for handling the error
    });

| Axios	| Fetch |
| ----- | ------- |
| Axios has url in request object. | 	Fetch has no url in request object. |
| Axios is a stand-alone third party package that can be easily installed. |	Fetch is built into most modern browsers; no installation is required as such.|
| Axios enjoys built-in XSRF protection. | Fetch does not. |
| Axios uses the data property.	| Fetch uses the body property. |
| Axios’ data contains the object. |	Fetch’s body has to be stringified. |
| Axios request is ok when status is 200 and statusText is ‘OK’. |	Fetch request is ok when response object contains the ok property. |
| Axios performs automatic transforms of JSON data. |	Fetch is a two-step process when handling JSON data- first, to make the actual request; second, to call the .json() method on the response. |
| Axios allows cancelling request and request timeout. |	Fetch does not.|
| Axios has the ability to intercept HTTP requests. |	Fetch, by default, doesn’t provide a way to intercept requests. |
| Axios has built-in support for download progress. |	Fetch does not support upload progress. |
## 17. What is UseState Hook ?(Implementation)
The React useState Hook allows us to track state in a function component.State generally refers to data or properties that need to be tracking in an application.
   # Implementation
       import React, { useState } from 'react';

     function Example() {
     // Declare a new state variable, which we'll call "count"
      const [count, setCount] = useState(0);
      return (
      <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
    );
    }

## 18. What is useEffect Hook ?(Implementation)
useEffect :It allows us to implement all of the lifecycle hooks from within a single function API.
// this will run when the component mounts and anytime the stateful data changes
      React.useEffect(() => {
          alert('Hey, Nads here!');
      });

// this will run, when the component is first initialized
      React.useEffect(() => {
          alert('Hey, Nads here!');
      }, []);

// this will run only when count state changes
      React.useEffect(() => {
          fetch('nads').then(() => setLoaded(true));
      }, [count]);

// this will run when the component is destroyed or before the component is removed from UI.
      React.useEffect(() => {
          alert('Hey, Nads here');
          return () => alert('Goodbye Component');
      });
      import React, { useState, useEffect } from 'react';

       function Example() {
      const [count, setCount] = useState(0);

      // Similar to componentDidMount and componentDidUpdate:
      useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
      });

      return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
     );
     }

## 19. What is UseReducer Hook ?(Implementation)
It does very similiar to setState, It's a different way to manage state using Redux Pattern. Instead of updating the state directly, we dispatch actions, that go to a reducer function, and this function figure out, how to compute the next state.

  # Implementation: const initialState = {count: 0};

       function reducer(state, action) {
      switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    default:
      throw new Error();
      }
     }

    function Counter() {
     const [state, dispatch] = useReducer(reducer, initialState);
     return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
     );
     }
      
## 20. What is UseMemo Hook ?(Implementation)
The React useMemo Hook returns a memoized value.Think of memoization as caching a value so that it does not need to be recalculated.The useMemo Hook only runs when one of its dependencies update.This can improve performance.
The useMemo and useCallback Hooks are similar. The main difference is that useMemo returns a memoized value and useCallback returns a memoized function. You can learn more about useCallback in the useCallback chapter.

      const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);

## 21. What is UseRef Hook ?(Implementation)
The useRef Hook allows you to persist values between renders.It can be used to store a mutable value that does not cause a re-render when updated.It can be used to access a DOM element directly.
 
        function TextInputWithFocusButton() {
        const inputEl = useRef(null);
        const onButtonClick = () => {
       // `current` points to the mounted text input element
    inputEl.current.focus();
      };
      return (
       <>
        <input ref={inputEl} type="text" />
        <button onClick={onButtonClick}>Focus the input</button>
       </>
      );
     }

