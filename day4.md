## 21. What is UseRef Hook ?(Implementation)
The useRef Hook allows you to persist values between renders.It can be used to store a mutable value that does not cause a re-render when updated.It can be used to access a DOM element directly.
 
  # for Implementation: please go through src folder --> Hookes Folder. --> UseRef.js

## 22. What is Context api?
The Context API is a React structure that enables you to exchange unique details and assists in solving prop-drilling from all levels of your application.
                        (or)
Context provides a way to pass data through the component tree without having to pass props down manually at every level.

For example, authenticated users, locale preferences, UI themes need to be accessed in the application by many components.

const {Provider, Consumer} = React.createContext(defaultValue)

## 23. Difference between callback and useCall back Hook ?
 callback is like an argument passed to an function whereas another one is hook, in this you pass another function as an argument.
   # for useCallback Implementation: please go through src folder --> Hookes Folder. --> UseMemo.js

  The callback function is invoked when setState finished and the component gets rendered. Since setState() is asynchronous the callback function is used for any post action.
  Note: It is recommended to use lifecycle method rather than this callback function.

     setState({ name: 'John' }, () => console.log('The name has updated and component re-rendered'))

## 24. What is Props Drilling Concept ?What is State Uplifting ?
  # Prop Drilling : 
  It is the process by which you pass data from one component of the React Component tree to another by going through other components that do not need the data but only help in passing it around.
  # State Uplifting:
  When several components need to share the same changing data then it is recommended to lift the shared state up to their closest common ancestor. That means if two child components share the same data from its parent, then move the state to parent instead of maintaining local state in both of the child components.

## 25. Difference between useEffect and useContext ?
  # useEffect :
  It allows us to implement all of the lifecycle hooks from within a single function API.
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
  # useContext :
  This hook allows us to work with React's Context API, which itself a mechanism to allow us to share data within it's component tree without passing through props. It basically removes prop-drilling
      const ans = {
          right: '✅',
          wrong: '❌'
      }

      const AnsContext = createContext(ans);

      function Exam(props) {
          return (
              // Any child component inside this component can access the value which is sent.
              <AnsContext.Provider value={ans.right}>
                  <RightAns />
              </AnsContext.Provider>
          )
      }

      function RightAns() {
          // it consumes value from the nearest parent provider.
          const ans = React.useContext(AnsContext);
          return <p>{ans}</p>
          // previously we were required to wrap up inside the AnsContext.Consumer
          // but this useContext hook, get rids that.
      }
