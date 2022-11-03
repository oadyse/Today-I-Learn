# Today-I-Learn #14 (Last Day in Week 3)
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
November 3th, 2022

## A whole material that i learnt in this week, so this is the timeline

**I ALREADY LEARNT MANY THINGS ON THIS WEEK ABOUT REACT**

- **Friday** : Friday is our orientation day for the week 3 and I got new team. 
  We had a team task and we need to fill our identity in the notion [Team 4 Task](https://teamsparta.notion.site/Team-4-Team-Task-Notion-Page-030c2d5bd56f477e8c868765202b793a)
- **Saturday & Sunday** : is time to learn new lecture about [React Mastery Lecture Notes](https://teamsparta.notion.site/React-Mastery-Lecture-Notes-020e0fd5425346e885ddc86750132997)
- **Monday** : [Week #3/TIL #10.md](https://github.com/oadyse/Today-I-Learn/blob/main/Week%20%233/TIL%20%2310.md)
- **Tuesday** : [Week #3/TIL #11.md](https://github.com/oadyse/Today-I-Learn/blob/main/Week%20%233/TIL%20%2311.md)
- **Wednesday** : [Week #3/TIL #12.md](https://github.com/oadyse/Today-I-Learn/blob/main/Week%20%233/TIL%20%2312.md)

## Today Quiz Answer

### 1. The added item won't appear on the screen when you click the add button.

- Answer:

  The added item won't appear on the screen when you click the add button because,
  the code haven't utilized the addTodo function. This function is redux.

- Code:

  ***Add "const dispatch = useDispatch();" at the line 9 of From.jsx before the state.***

  ```js
    const dispatch = useDispatch();
    const [todo, setTodo] = useState({
      id: 0,
      title: "",
      body: "",
      isDone: false,
    });
  ```

  ***Add "dispatch(addTodo({ ...todo, id }))" at the line 25 of Form.jsx.***
  ```js
    dispatch(addTodo({ ...todo, id }));
    setTodo({
      id: 0,
      title: "",
      body: "",
      isDone: false,
    });
  ```


### 2. The existing items disappear when you click add button.

- Answer:

  The existing items disappear when you click add button because,
  we haven't saved any additional data into useState which we have initialized before.

- Code:

  ***We need to change code ADD_TODO at line 63 of todos.js***
  ```js  
    case ADD_TODO:
        return {
            ...state,
            todos: [...state.todos, action.payload],
        };
  ```

### 3. The delete function won’t work.

- Answer:

  The delete function won’t work because, 
  we haven't made or initialized case named DELETE_TODO in action State.

- Code:

  ***We can add ase DELETE_TODO in action State of todos.js***
  ```js
    case DELETE_TODO:
        return {
            ...state,
            todos: state.todos.filter((todo) => todo.id !== action.payload),
        };
  ```

### 4. Data won’t update when you enter details page.

- Answer:

  Data won’t update when you enter details page because, 
  we need to use a function which can return the value of the detail data based on the selected ID.

- Code:

  ***Add this function in Detail.jsx before the return.***
  ```js
    useEffect(() => {
      dispatch(getTodoByID(id));
    }, [dispatch, id]);
  ```

### 5. Correct data won’t load when entering details page of the cards marked done.

- Answer:

  Correct data won’t load when entering details page of the cards marked done because,
  the link to the details page still uses the index value of the todos array as a reference. 
  We only need todo.id to return the value.

- Code:

  ***Change the value at line 61 of List.jsx***
  ```js
    <StLink to={`/${index}`} key={todo.id}>   ❌
    <StLink to={`/${todo.id}`} key={todo.id}>   ✅
  ```

### 6. The cancel button won’t work.

- Answer:

  The cancel button won’t work because, We need to add the selected id parameter into the 'onToggleStatusTodo' function.

- Code:
  
  ***Change the code at line 77 of List.jsx***

  ```js
  onClick={onToggleStatusTodo}   ❌
  onClick={() => onToggleStatusTodo(todo.id)}   ✅
  ```

## Documentation

![image](https://user-images.githubusercontent.com/62550785/199770527-c0e21b39-5d38-41c2-bb70-23cbab190741.png)
