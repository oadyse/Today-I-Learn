# Today-I-Learn #10
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
October 31th, 2022

## Introduce

Today was such a tiring day for me. I was trying to survive for this class at least on this night. 
But finally I can finish this class until I write this TIL today.

Today we had presentation team task after we finished the questions.

![image](https://user-images.githubusercontent.com/62550785/199056716-1d41dc4d-be39-44be-817e-143481add2ba.png)

## Answer the Questions
- **Component A is subscribing Redux store. If the data saved in Redux has changed, (Let’s say that the variable that A is subscribing has changed) in what process does component A go through to get the changed variable? Demonstrate the flow (use pictures, presentation slides, hand-drawn, etc)**
  
  *Answer:*
  
  The state changer in redux is called reducer. Redux save states in every component that can be accessible to every component 
  (ignoring parent child relation). When we change the state, we use reducer. To change this state, you need to make some command 
  action in your redux and use condition when the command meet to let the reducer changes the state. This command is Dispatcher. 
  After changed, the new state will visualize in View. 

  ![image](https://user-images.githubusercontent.com/62550785/199052737-f127a855-5f0f-4553-829f-d86887c536ed.png)
  ![image](https://user-images.githubusercontent.com/62550785/199056950-44ae829e-f516-456a-b705-573d984aedca.png)

##

- **What is optional chaining? In what circumstance do we use it?**
  
  *Answer:*
  
  We usually use ``` . ``` for accessing the properties of an object. This method only works if the properties that are accessed
  are not ``` null ``` or ``` undefined ```. If the properties are ``` null ``` or ``` undefined ```, it causes an error. 
  The example are shown on the code below:
  
  ```js
  const user = {
	name: 'John',
  cat: {name: 'Cookie'}
  }

  console.log(user.cat.name) // Cookie

  console.log(user.address) // undefined

  console.log(user.cat.age) // undefined

  console.log(user.dog.name) // error
  ```
  
  Optional chaining operator ``` ?. ``` can access the ``` null ``` or ``` undefined ``` properties without causes an error. 
  Instead of causing an error, it returns ``` undefined ```. The example are shown on the code below:
  
  ```js
  const user = {
	name: 'John',
  cat: {name: 'Cookie'}
  }

  console.log(user.dog?.name) // undefined
  ```
  
  In conclusion, optional chaining operator ``` ?. ``` is deeper than operator ``` . ``` in checking the existence of a property in an object.

##

- **If you use <button type="submit"> when you use <form>, Redux data is initialized. Explain why?**
  
  *Answer:*
  
  When in redux, the state changed using reduce function that sends action, receive, and doing conditional to check if the 
  condition met to change the state. When submit forms using button form, redux state changed too but the value is provided 
  on initialValues prop or reduxForm() config paramater so when the submit button is submitted the value of filled form and 
  the initialValues will initialize the value and loaded into the form state. 

##  

- **What method do you have to use to maintain the data within Redux after refreshing?**
  
  *Answer:*
  
  * **When we refresh the browser, our data will be lost.**
    
    That’s why we need to use Redux Persist to save the state in persistent storage so that even after a refresh, 
    the data will still remain intact.
  
  * **How to Persisting state with Redux Persist?**
  
    a. First, we’ll add Redux Persist to our app with the following command:
    ```npm install --save redux-persist``` OR ```yarn add redux-persist```
    
    b. We will configure our store.js such as:
    
    ![image](https://user-images.githubusercontent.com/62550785/199055718-4bf0095d-5bf7-4203-a2eb-aeecd3b96c4e.png)
    
    c. Then, in the index.js
  
    ![image](https://user-images.githubusercontent.com/62550785/199055814-49fcded2-5ab8-438a-9492-1612ae88e582.png)

    *We simply wrap our App with the ```PersistGate``` component by passing persistor as a prop created earlier in the ```store.js``` file. 
    If all went well, we should have the app persisting the state.*
