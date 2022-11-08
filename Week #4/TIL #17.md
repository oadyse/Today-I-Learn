# Today-I-Learn #17
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
November 8th, 2022

## ✨ DIY Section ✨

### 🔑 What is Redux Thunk, what is its use and what code we need to install Redux Thunk?
  
   Redux Thunk is middleware that allows us to dispatch functions rather than objects. 
   So we can dispatch (function) instead of dispatch (object). 
  
   We know that Redux returns in the form of props actions defined by Reducers, 
   but the problem is that if we want to return a function, Redux can't handle it.
  
   Therefore, we need a working middleware to return the action. So, Redux Thunk 
   is a middleware that allows writing Actions that return functions instead of actions.
  
   > *We can type this code in terminal and run it to install Redux Thunk.*

    yarn add react-redux @reduxjs/toolkit

### 🔑 What are some advantages of using Axios over other HTTP libraries like jQuery AJAX?
   
   Axios is a promise-based HTTP library that provides a simpler, cleaner interface for making AJAX requests. 
   It also has a number of other advantages over jQuery AJAX, including automatic transforms for JSON data, 
   support for canceling requests, and built-in support for progress tracking.
   
### 🔑 What is Promise Chaining?

  Promise Chaining is a simple concept by which we may initialize another promise inside our .then() 
  method and accordingly we may execute our results.

  - **Input**
    
    ```jsx
    let promise = new Promise((resolve, reject) => {
      resolve("Hello Sparta");
    });
    promise
      .then(
        new Promise((resolve, reject) => {
          resolve("Hello CodingClub");
        }).then((result1) => {
          console.log(result1);
        })
      )
      .then((result2) => {
        console.log(result2);
      });
    ```
    
    - **Output**
    
      As illustrated above, while executing the declared promise we are passing another promise inside the **`.then()`** 
      and executing our results accordingly.

## Documentation

![Screenshot (193)](https://user-images.githubusercontent.com/62550785/200634843-cd99d121-6a19-4c74-b625-0dbda73e7359.png)
