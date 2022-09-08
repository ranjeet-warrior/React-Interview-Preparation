26. High Order Component in react js ?
A higher-order component (HOC) is a function that takes a component and returns a new component. Basically, it's a pattern that is derived from React's compositional nature.
We call them pure components because they can accept any dynamically provided child component but they won't modify or copy any behavior from their input components.
      const EnhancedComponent = higherOrderComponent(WrappedComponent)

  # for Implementation: please go through src folder --> HOC foder.

## 27. Do you know about SEO ? Is it true that react js supports SEO support?
Search engine optimisation (SEO) is the process of improving the quality and quantity of website traffic to a website or a web page from search engines. SEO targets unpaid traffic (known as “natural” or “organic” results) rather than direct traffic or paid traffic.
React helps build a very user-friendly UI that is also valuable by SEO, so you definitely shouldn't avoid it while creating a user interface for your app/website. However, you should use some tricks to ensure that your React-site is understandable for Google crawlers and, therefore, good for SEO.

## 28. clean up in useEffect.
clean up function: this function gets executed when the component is unmounted from the screen. This is mostly used for memory leaks.
   //componentWillUnmount : Cleanup function in useEffect.
      useEffect(() =>{
        console.log("Inside useEffect hook");

        return function cleanup() {
            console.log("componentWillUnmount is happen...!")
        }
      })

## 29. What is the use of useMemo and useCallback?
 # Use of useMemo: 
 React has a built-in hook called useMemo that allows you to memoize expensive functions so that you can avoid calling them on every render. You simple pass in a function and an array of inputs and useMemo will only recompute the memoized value when one of the inputs has changed.
 # Use of useCallback:
 useCallback will return a memoized version of the callback that only changes if one of the dependencies has changed. This is useful when passing callbacks to optimized child components that rely on reference equality to prevent unnecessary renders.

## 30. Why do we need keys in react less?
The main purpose of keys is to help React differentiate and distinguish elements from each other, increasing its performance when diffing between the virtual and real DOM. To use keys, simply add the prop inside an element such as <li> . Unique IDs are the best value to assign to keys.
                                 (or)
"Key" prop is used to look pretty, and there is no benefit whatsoever. "Key" prop is a way for React to identify a newly added item in a list and compare it during the "diffing" algorithm. It is one of the attributes in HTML. It is NOT commonly used in an array.

## 31. Do you know about redux?
Redux is a pattern and library for managing and updating application state, using events called "actions". It serves as a centralized store for state that needs to be used across your entire application, with rules ensuring that the state can only be updated in a predictable fashion.
Here is a small example of react and Redux application. You can also try developing small apps. Sample code for increase or decrease counter is given below − This is the root file which is responsible for the creation of store and rendering our react app component. /src/index.
