# React-Interview-Preparation
  Day 1
 
 1. What is Virtual DOM ?

 Ans. As Stated by React team,Virtal DOM is the concept where a virtual representation of Real DOM is kept inside the memory and is synced
      with real DOM by a library such as ReactDOM
      DOM manipulation is an integral part of any web application,but DOM manipulation is quite slow when compared to other operations in 
      JavaScript.The efficiency of application gets affected when several DOM manipulation are being done.Most JavaScript framework updates 
      the entire DOM even when small part of DOM changes
      
2. What is SPA(Single Page Application)


Ans. A SPA(Single Page Application) is essentially web page that interacts with web browser dynamically by rewriting the current webpage
     with the data obtained from the webserver.Hence,in Single Page Application,the web page doesnot reload the page during its runtime and
     instead works within a browser.
     
3. What is the differnce between class and functional component?
Ans. Before the introduction of Hooks in React,functional component were called stateless component and were behind class components on a 
     feature basis.After the introduction of Hooks functional component is equals to class component
     Although,functional component is the new trend,react team insists on keeping class component in React.Therefore it is important to know 
     how the components differ
     Declaration:-
                    
                    
                    function card(props){
                    return(
                    <div className = "main-container">
                    <h2>Title of Card</h2>
                    </div>
                    )
                    }
                    
                    const cars = (props) =>{
                    <div className = "main-container">
                    <h2>Title of card</h2>
                    </div>
                    )
                    }
                    }
  Class component on the other hand,are declared using ES6 class
  
 
                     class card extends React.component{
                     constructor(props){
                     super(props);
                     }
                     render(){
                     return (
                    <div className = "main-container">
                     <h2>Title of Card</h2>
                    </div>
                   )
                   }
                   }
       
   Handling props :
       Let's render following component with props and analyse how functional and class component handle props
       
       <StudentInfo name = "Ranjeet" roll no = "BE/15244/16"/>
   In funcional component handling of props is pretty straight forward.Any prop provided as an argument to a functional component can be
   directly used inside HTML element.
   
  
                     function StudentInfo(props){
                     return(
                     <div ClassName = "main">
                     <h2>{props.name}</h2>
                     <h4>{props.roll no}</h4>
                     </div>
                  )
                  }
   In case of class componets props are handled in different way :
   
                 class StudentInfo extends React.Component{
                 constructor(props){
                 super(props);
                 }
                 render(){
                 return{
                 <div className = "main">
                 <h2>{this.props.name}</h2>
                 <h4>{this.props.roll no}</h4>
                 </div>
                 )
                 }
                 }
 As we can see this keyword is used in class component
 
 Handling State:
 Functional componets uses React Hook to handle state,It uses the usetate hook to set the state of a variable inside component
              
                  function ClassRoom(props){
                  let[studentcount,setstudentcount] = usestate(0);
                  const addstudent = () =>{
                  setstudentcount(++setstudentcount);
                  }
                  return(
                  <div>
                  <p>No of Students in the Class Room :{studentcount} </p>
                  <button onClick = {addStudent}>Add Student</button>
                  </div>
                  )
                  }
 since usestate hook returns an array of two items,the first item contains the current state and second term is a function used to update state.
 
 In the code above using array destructuring we have set Variable name studentcount, with current value of '0' and setStudentcount is the function
 i.e used to upadte state
 
 for reading state,we can see from the above code,variable name can be directly used to read current state of variable
 We cannot use React Hooks inside class components,therefore state handling is done very differently in a class component
 Let's take same above example and convert it into class component
 
                class classRoom extends React.Component{
                constructor(props){
                super(props);
                this.state = {studentscount:0};
                this.addstudent = this.addstudent.bind(this);
                }
                addstudent(){
                this.setstate(prevstate) => {
                return {studentcount:prevstate.studentcount++}
                });
                }
                render(){
                return{
                <div>
                <p>Number of Students in classroomn:{this.state.studentcount}</p>
                <button onClick = {this.addStudent}>Add Student</button>
                </div>
                )
                }
         }
  In the above code,we see we are using this.state to add variable studentcount and setting the value to "0"
  for rendering state, we are using this.state.studentscount
  for updating state. we need to first bind addstudent function to this only then, we will be able to use setstate function which is used to
  update state.
                
 4.What do you mean by state and its use in react?
 
 Ans. The state is a built-in React object that is used to contain data or information about the Component.A Component's state can change
      over tim, whenever it changes,the Component re-renders.The change in state can happen as a response to user action or system generated
      events and these changes determine the behaviour of the component and how it will render
      
                        class Greeting extends React.component{
                        state = {
                        name : "Ranjeet"
                        };
                        updateName(){
                        this.setState({name:"Ranjeet"});
                        }
                        render(){
                        return(
                        <div>
                        {this.state.name}
                        </div>
                        )
                        }
                        }
  It is used to conatin data or information about the component.                   
 
 5. What is JSX and why do we need it instead of Js?

Ans. JSX Stands for JavaScript XML. It allows us to write HTML inside JavaScript and place them in the DOM without using functions like
     appendChild() or createElement().
     As stated in the official docs of react,JSX provides syntactic sugar for React.createElement() function.
     Let's understand how JSX works :
      
                      const container = ( <div>
                    <p>This is a text</p> </div>
                    ); ReactDOM.render(container,rootElement);
      
 6. What is package.json?
 
 Ans. The package.json file is the heart of Node.js system. It is the manifest file of any Node.js project and contains the metadata of the project. The package.json file is the essential part to understand, learn and work with the Node.js. It is the first step to learn about development in Node.js. 
 
7. What is differnce between React and React Native ? which one is library or framework?

Ans. React is a Javascript library,supporting both front end web being run on server,for building user interfaces and web applications.It follows concept
     of reusable components
    React Native is a mobile framework that makes use of Javascript engines available on the host, allowing to build mobile applications for different
   platforms (iOS,Androidand Windows Phone) in JavaScript that allows you to use ReactJS to bild reusable components nad communicate with native    components 
          React is a JavaScript library and React Native is a JavaScript framework
          
 8. What is the package name you are using for routing implementation?
          
Ans. BrowserRouter

9. How do you pass data from parent to child?

Ans. By using props we can pass data from parent to child

10 What is lazy loading in react ?

Ans. Lazy loading means that a component or part of code must gets reloaded when it requires.
     
     
