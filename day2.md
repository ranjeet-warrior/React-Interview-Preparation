7. What is the Difference between react and react native? Which one is library or framework?

React and React Native are developed by Facebook and have gained a huge fan base in a short time. React is known as ReactJs, which is a JavaScript library to build single-page web applications.

Besides, React Native is a React JS-based framework to design mobile apps. Moreover, with reusable components, you can develop native mobile applications.

React is a JavaScript library of reusable components designed to create skeletons of the apps, whereas React Native is designed to build native mobile apps with reusable components. React is an open-source JS library for building the UIs for web applications; besides, React Native is used to build rich mobile UI from declarative components using only JavaScript. Both React and React Native are ruling the industry and are widely used for mobile and web applications. However, the difference between web apps vs websites will not affect your user.

Which one is library or framework?

React is an open source JavaScript framework, that isn't actually a framework. But it is currently the most commonly used front-end development technology in the world. React, originally developed by and still maintained by Facebook and supported by an active open source community, is in fact a JS 'library'. React Native is a JavaScript framework for writing real, natively rendering mobile applications for iOS and Android. It's based on React, Facebook's JavaScript library for building user interfaces, but instead of targeting the browser, it targets mobile platforms.

Why is react a library and react-native a framework?

Reactjs, eventually, is a JavaScript library, which enables the programmer to create an engaging and high performing UI Layer while React Native is an entire framework for building cross-platform apps, be it web, iOS or Android.

8. What is the package name you are using for routing?

React Router is a standard library system built on top of the React and used to create routing in the React application using React Router Package.In this Browser Router as Router, Routes and Route and NavLink get imported from react-router-dom. React Router DOM enables you to implement dynamic routing in a web app. Unlike the traditional routing architecture in which the routing is handled in a configuration outside of a running app, React Router DOM facilitates component-based routing according to the needs of the app and platform.

9. What is package.json?

It contains the information about the project and also contains the libraries which the project is using and it also has the description of the commands which gets used to run test or build your project.

10. Routing Implementation:

Please see in src folder --> Routing Folder..

11. How do you pass data from parent to child?

please go through src folder --> Data-p2c

12. What is lazy loading in react ?

In essence, lazy loading means that a component or a part of code must get loaded when it is required. It is also referred to as code splitting and data fetching . Talking about React specifically, it bundles the complete code and deploys all of it at the same time.

Example:An example of image lazy-loading can be found on the popular publishing platform Medium, which loads lightweight placeholder images at page load, and replaces them with lazily-loaded images as they're scrolled into the viewport. An example of image lazy-loading in action.

Benefits: The benefits of lazy loading include: Reduces initial load time – Lazy loading a webpage reduces page weight, allowing for a quicker page load time. Bandwidth conservation – Lazy loading conserves bandwidth by delivering content to users only if it's requested.

13. Difference b/w Stateful and stateless Component.

Stateless:

If the behaviour is independent of its state then it can be a stateless component. You can use either a function or a class for creating stateless components. But unless we need to use a lifecycle hook in your components, we should go for function components. There are a lot of benefits if you decide to use function components here; they are easy to write, understand, and test, a little faster, and you can avoid the this keyword altogether.

Stateful:

If the behaviour of a component is dependent on the state of the component then it can be termed as stateful component. These stateful components are always class components and have a state that gets initialized in the constructor. class App extends Component { constructor(props) { super(props) this.state = { count: 0 } }

  render() {
    // ...
  }
}
React 16.8 Update: Hooks let you use state and other React features without writing classes. The Equivalent Functional Component import React, {useState} from 'react';

const App = (props) => {
  const [count, setCount] = useState(0);

  return (
    // JSX
  )
}
14. How do you switch one component to another?

Way to Switch/Navigate from one page to another page

Link

NavLink

Redirect Component

history.push

history.replace

Link Link is used to manage the navigation and it worked as an anchor tag. Check below code for the demonstration. import { Link } from 'react-router-dom'; ... ...

About
NavLink NavLink behaves the same as Link but in addition, it comes with a new attribute called “activeClassName” which helps us to add the class to the anchor tag when page url will match.

import { NavLink } from 'react-router-dom'; ... ... About
