# [Table of contents]()

| No. | Questions                                                                                                                                         |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | [What are the possible ways to create objects in JavaScript](#what-are-the-possible-ways-to-create-objects-in-javascript)                         |
| 2   | [What is a callback Function?](#what-is-a-callback-function)                                                                                      |
| 3   | [What is Promise?](#what-is-promise)                                                                                                              |
| 4   | [What do you understand by LocalStorage and sessionStorage?](#what-do-you-understand-by-localstorage-and-sessionstorage)                          |
| 5   | [What is Hoisting in Javascript?](#what-is-hoisting-in-javascript)                                                                                |
| 6   | [What are Higher Order Functions?](#what-are-higher-order-functions)                                                                              |
| 7   | [What is a anonymous function?](#what-is-a-anonymous-function)                                                                                    |
| 8   | [What are the first class functions in javaScript?](#what-are-the-first-class-functions-in-javascript)                                            |
| 9   | [How can We change class based components to fuctional based components](#how-can-we-change-class-based-components-to-fuctional-based-components) |
| 10  | [What are Higher Order Functions?]()                                                                                                              |

1. ### What is the closure?

   A Closure is the cobination of functions bundled together with references to its surrounding state ( lexical environment ).
   In other words, a closure gives you access to an outer function's scope from an inner function.

   -  functions in JavaScript form closures.

   ```javascript
   function firstFunc() {
   	let name = "javaScript"; // name is a local variable created by firstFunc
   	function secondFunc() {
   		// secondFunc() is the inner function, a closure
   		console.log(name); // use variable declared in the parent function
   	}
   	return secondFunc;
   }
   const myFunc = firstFunc();
   myFunc();
   ```

**[⬆ Back to Top ](#table-of-contents)**

2. ### What is a callback Function?

   A callback function is a function is passed as an argument to another function and invoked inside the parent function.

   ```javascript
   function parentFunc(callback) {
   	setTimeout(() => {
   		callback();
   	}, 1000);
   }

   function childFunc() {
   	console.log("Namaste World!");
   }

   parentFunc(childFunc);
   ```

**[⬆ Back to Top ](#table-of-contents)**

3. ### What is promise?

   A Promise is an object representing the eventual completion or failure of an asynchronous operation.

   ```javascript
   new Promise((resolve, reject) => {
   	console.log("initial");
   	resolve("resolved");
   })
   	.then((value) => {
   		console.log(value);
   		throw new Error("Something failed");
   		console.log("Do Something");
   	})
   	.catch((err) => console.error(err))
   	.then(() => console.log("Do this no matter what is happenig above"));
   ```

**[⬆ Back to Top ](#table-of-contents)**

4. ### What do you understand by LocalStorage and sessionStorage?

   localStorage is read only propery of the window interface allows you to access a storage object for the document's origin.

   -  localStorage data has no expiration time.

   ```javascript
   // Save data to localStorage
   localStorage.setItem("key", "value");

   // Get saved data from localStorage
   let data = localStorage.getItem("key");

   // Remove saved data from localStorage
   localStorage.removeItem("key");

   // Remove all saved data from localStorage
   localStorage.clear();
   ```

   The read-only sessionStorage property accesses a session Storage object for the current origin.

   -  data in sessionStorage is cleared when the page session ends.

   ```javascript
   // Save data to sessionStorage
   sessionStorage.setItem("key", "value");

   // Get saved data from sessionStorage
   let data = sessionStorage.getItem("key");

   // Remove saved data from sessionStorage
   sessionStorage.removeItem("key");

   // Remove all saved data from sessionStorage
   sessionStorage.clear();
   ```

**[⬆ Back to Top ](#table-of-contents)**

5. ### What is Hoisting in Javascript?

   JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables or classes to the top of their scope, prior to execution of the code.

   ```javascript
   //we can invoke function before it declared
   myFunc();

   function myFunc() {
   	console.log("Function are hoisted in Nature");
   }

   console.log(a); // undefined
   //only declarations are hoisted not initialization
   var a = 12;
   ```

**[⬆ Back to Top ](#table-of-contents)**

6. ### What are Higher Order Functions?

   A function that returns a function or takes other functions as arguments is called a higher-order function.

   ```javascript
   let radius = [12, 13, 14]; //radius of circles

   const area = function (radius) {
   	return Math.PI * radius * radius;
   };

   const output = function (array, logic) {
   	const output = [];
   	for (let i = 0; i < array.length; i++) {
   		output.push(logic(array[i]));
   	}
   	return output;
   };

   console.log(output(radius, area)); //we are passing area function to output
   ```

**[⬆ Back to Top ](#table-of-contents)**

7. ### What is a anonymous function?

   Function without a names is called a anonymous function.

   ```javascript
   var func = function () {}; //this is a anonymous function
   func();
   ```

**[⬆ Back to Top ](#table-of-contents)**

8. ### What are the first class functions in javaScript?

   A function is said to be first class function when they treated like variable.

   -  Ability to used functions as variables.

   ```javascript
   function sayHello() {
   	return "Hello";
   }

   function greetings(helloMSG, name) {
   	return helloMSG() + name;
   }

   greetings(sayHello, " Aditya");
   ```

**[⬆ Back to Top ](#table-of-contents)**

9. ### How can We change class based components to fuctional based components?

   If the component needs state or lifecycle method then use class component otherwise use function component.However, from React 16.8 with the addition of hooks, you could use state, lifecycle method and other feature that were only available in class component right in you function component.So it is always recommended to use Function components, unless you need a React functionality whose Function component equivalent is not present yet, like Error Boundaries.

   ```javascript
   // creation of state in class based components
   class classComponent {
      constructor(){
   	this.state = {
        name = '',
      }}
   componentDidMount(){
      // Mounting: // called before the componnet is displayed on the  UI
    }
   componentDidUpdate(){
      // caused by a change to state which rerenders the component

   };
   render(){
      return jsx;
   }
   }

   * Functional Component*
   //creation of state in functional based components
   import React, {useState} from 'react';
   function funcComponent(){
      const [name,setName] = useState('');
      useEffect(()=>{
         return // called right before your UI is rendering the component
      },
      []// runs on updating
      ) // replaces componentDidMount() and componentDidUpdate

   return jsx;
   }
   ```

   <a href ="notion.so/akashjdotcom/React-Project-Swipe-File/cb88a73845f24b2e9a88590a2cbf5316">
   <img src = "./images/useEffect.png"/>
   </a>
   <img src = "./images/react-lifecycle.jpeg" />

**[⬆ Back to Top ](#table-of-contents)**

10.   ### Javascript map filter reduce.

      map() function is used to iterate on elements of an array and it is a higher order function.

      ```javascript
      let array = [12, 13, 14, 15, 16];
      array.map((item, index, array) => {
      	return item * 2;
      });

      // Output [24, 26, 28, 30, 32]
      ```
