# Today-I-Learn #19 (Last TIL in week 4)
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
November 10th, 2022

## Question 1:

### a) What are Higher-Order Components? 

Higher-order Component (HOC) is a technique in ReactJs that used to create new components from existing components.
So, we create a new component that has a new feature/function, by combining it with other components.

### b) Give an example of a High Order Component and its use.

```js
import React from 'react'

const student = grade => {
  class HOC extends React.Component {
    render() {
      return <grade />
    }
  }
  return HOC
}
```
>*In the above example, student is a function that takes a component called grade as an argument. 
We have created a new component called HOC which returns the <grade/> from its render function. 

##

## Question 2:

### a) What is reconciliation in React? 

Reconciliation is the process through which React updates the DOM. 
When a component’s state changes, React has to calculate if it is necessary to update the DOM. 
It does this by creating a virtual DOM and comparing it with the current DOM. 
In this context, the concept of Virtual DOM used by React makes rendering much faster.

### b) Why can reconciliation make React faster?

The browser builds the DOM by parsing the code we write, it does this before it renders the page. 
The problem with the DOM is that it is not optimized for dynamic UI applications. 
So, updating the DOM can slow your application when there are a lot of things to be changed, 
as the browser has to reapply all styles and render new HTML elements. 

##

## Question 3:

### a) What is Flux?

Flux is a programming concept where data is unidirectional. This is where data enters an application and flows in one direction until it is rendered in the view.

### b) Explain in detail the difference with MVC

>***Flux has 4 components:***
- **Action** : An action that is sent to the Dispatcher to execute the data flow (Data flow)
- **Dispatcher/Reducer** : This is the central hub of the application. All data is sent through the Dispatcher and stored in the store
- **Store** : Store is a place where the state (State) and application logic is stored. Each store maintains a certain state and will be updated when needed.
- **View** :View receives data from store then renders back to app

>***MVC has 3 components:***
- **Model** : the first component of MVC is a model that functions to prepare, organize, and even manipulate data in the database.
- **View** : serves to present information in the form of a Graphical User Interface or GUI for short.
- **Controller** : serves to connect and control the model and view so that they can be connected to each other.

### c) Give examples of code differences between those two.

### >***FLUX***

- Action
```js
  const ADD_TODO = "ADD_TODO";
  export const addTodo = (payload) => {
    return {
        type: ADD_TODO,
        payload,
    };
  };
```
- Dispatcher/Reducer
```js
  const todos = (state = initialState, action) => {
    switch (action.type) {
        case ADD_TODO:
            return {
                ...state,
                todos: [...state.todos, action.payload],
            };
        default:
            return state;
    }
  };

  export default todos;
``` 

- Store
```js
  import { createStore } from "redux";
  import { combineReducers } from "redux";
  import todos from "../modules/todos.js";

  const rootReducer = combineReducers({
      todos,
  });
  const store = createStore(rootReducer);

  export default store;
```
- View
```js
import React, { useState } from "react";
import styled from "styled-components";
import { useDispatch } from "react-redux";
import nextId from "react-id-generator";

const Form = () => {
  const id = nextId();

  const dispatch = useDispatch();
  const [todo, setTodo] = useState({
    id: 0,
    title: "",
    body: "",
    isDone: false,
  });

  // const todos = useSelector((state) => state.todos.todos);
  const onChangeHandler = (event) => {
    const { name, value } = event.target;
    setTodo({ ...todo, [name]: value });
  };

  const onSubmitHandler = (event) => {
    event.preventDefault();
    if (todo.title.trim() === "" || todo.body.trim() === "") return;

    dispatch(addTodo({ ...todo, id }));
    setTodo({
      id: 0,
      title: "",
      body: "",
      isDone: false,
    });
  };

  return (
    <StAddForm onSubmit={onSubmitHandler}>
      <StInputGroup>
        <StFormLabel>Title</StFormLabel>
        <StAddInput
          type="text"
          name="title"
          value={todo.title}
          onChange={onChangeHandler}
        />
        <StFormLabel>Content</StFormLabel>
        <StAddInput
          type="text"
          name="body"
          value={todo.body}
          onChange={onChangeHandler}
        />
      </StInputGroup>
      <StAddButton>Add New</StAddButton>
    </StAddForm>
  );
};

export default Form;
```

### >***MVC***
- Model
```php  
  <?php
  class M_user extends CI_Model
  {
        public function insert_data($table, $data)
        {
        return $this->db->insert($table, $data);
        }
  }
```

- Controller
```php
  <?php
  class User extends CI_Controller 
  {
    public function add()
    {
        $this->load->view('user_add');
    }
  }
```

- View
```php
<!DOCTYPE html>
<html>
    <head>
        <title>Create Todo</title>
    </head>
    <body>
        <center>
            <form method="post" action="<?= base_url('user/save'); ?>">
                <table border="1">
                    <tr>
                        <td>Title</td>
                        <td><input type="text" name="title"></td>
                    </tr>
                    <tr>
                        <td>Content</td>
                        <td><input type="text" name="body"></td>
                    </tr>
                    <tr>
                        <td colspan="2"><input type="submit" name="kirim" value="Masukkan Data"></td>
                    </tr>
                </table>
            </form>
        </center>
    </body>
</html>
```
##
## Question 4:

### a) What is Redux?

Redux is state management in ReactJs. By using Redux, we simply create one state and that state can be accessed in any component.

### b) Explain in detail when (and when not) to use Redux

>***When should to use Redux?***

- We have a very large and complex application with many states required in many application places
- We need to add complex logic every time a certain state is updated
- Codebase is medium size or higher and has many contributors

>***When shouldn't you use Redux?***

- Small code base.
- An application consisting only of UI changes
- Top-level component props are only passed down as far as their children
- Applications that do not require a lot of data that are constantly updated

### c) What are the advantages of Redux compared to other state management such as MobX and Zustand?

There are many advantages of Redux that make it a management tool over other state management tools. 
The most notable benefit of Redux is the improved state management. Besides that :

- Redux can prevent Re-rendering/re-rendering.
- Redux optimizes the performance of large applications.
- Redux makes debugging easier
- Redux is useful in server-side rendering

##
## Question 5:

### a) What is Redux Thunk?

Redux Thunk is a middleware/bridge that allows you to call an action generator that returns a function instead of an action object. 
The function accepts a storage delivery method, which is then used to send a synchronous action within the function body after the asynchronous operation is complete.

##
## Question 6:

### a) What is code-splitting in general?

Code splitting is a technique for splitting code into several different files.

### b) Give an example of implementing code-splitting in React.

In react we use React.lazy() to do a code-splitting.
This is a component function that takes another function as an argument. 
This function performs a dynamic import and returns a promise as a result. 
React takes care of this promise.lazy(), which expects the returned module to contain the default export React components. 

- Before:
```js
import React from "react";
import Header from "../components/ui/Header";
import Layout from "../components/ui/Layout";
import Form from "../features/todos/components/Form";
import List from "../features/todos/components/List";

const Home = () => {
  return (
    <Layout>
      <Header />
      <Form />
      <List />
    </Layout>
  );
};

export default Home;
```
- After:
```js
import React, {lazy} from "react";
const Header = lazy(()=> import("../components/ui/Header"));
const Layout = lazy(()=> import("../components/ui/Layout"));
const Form = lazy(()=> import("../features/todos/components/Form"));
const List = lazy(()=> import("../features/todos/components/List"));

const Home = () => {
  return (
    <Layout>
      <Header />
      <Form />
      <List />
    </Layout>
  );
};

export default Home;
```
