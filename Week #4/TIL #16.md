# Today-I-Learn #16 (Last Day in Week 3)
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
November 7th, 2022

## What I've done today?

So today, I've done my team task which is I got 2 questions to answer from all of questions.

I will explain to you what I answered on this team task.

### **Promise**

> ***Promises are usually used for asynchronous or blocking code.***
> 

Promises have `resolve` and `reject` .

- `resolve` for **returned value is fulfilled.** `resolve` will be resolved in the `.then` function.
- `reject` for :
    - **returned value is not fulfilled.**
    - conditions where value cannot be returned and we are required to return an error value to the rejected promise `(catch)`
    
    `reject` will be resolved in the `.catch` function.
    
1. Promise has a `.then` function as a callback to return failure and success cases from Promise, which means we can call the callback function repeatedly to continue the existing value or just display different data values.
2. Promise has a `Promise.all` function which is usually used on every variable that is created first the promise to get the first result, then in `Promise.all` will be combined to get the same resolve result.

### **Async Await**Async returns a promise.

> ***Async returns a promise.***
> 

1. Inside the async function can use multiple await statements, where we can pass the result of the resolve of the await statement in the variable.
2. Await only uses a single promise (where the promise here is the condition if the value is fulfilled (on-fullfilled/resolved/settled)).
3. Await needs help with try catch for error handling, because await doesn't have an `onRejection` function, but has a rejected value to throw to catch.

### Promise Chaining

Promise Chaining is a simple concept by which we may initialize another promise inside our .then() 
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
    
    As illustrated above, while executing the declared promise we are passing another promise inside the **`.then()`** and executing our results accordingly.


## Documentation

- Like the normal day, we had a discussion time with my team, so in here we discuss about our team project.

  ![Screenshot (184)](https://user-images.githubusercontent.com/62550785/200369705-0cfaa091-2306-492f-914f-7c59649dfaab.png)

- We had a zoom meeting with Ms. Eunseo. This session was explaining the exam answer by choosed student.

  ![Screenshot (185)](https://user-images.githubusercontent.com/62550785/200369875-fc9feca5-b7dd-4d3e-b884-326eade0219b.png)
  
- After the zoom session, we discussed with other team about the material of React.
  ![Screenshot (187)](https://user-images.githubusercontent.com/62550785/200370447-2802ddd7-bf18-411c-abba-8d59e49799b9.png)  
