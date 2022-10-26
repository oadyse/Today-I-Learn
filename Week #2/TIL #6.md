# Today-I-Learn #6
October 24th, 2022

## Intro

Actually, I am continuing what I learn on Saturday, that is about React. Is that difficult to start? Kinda XD
Cus I dun have any experience with React before, so it's kinda difficult to start it.
My weekend so far was good, I could take a rest for awhile at least.
I was laying on my bed, feel like this is holyday :).

- I got a message about how was the video lesson yesterday about React from Ms. Eunseo. I gave a feedback for it. 
I can say for beginner in React is not that hard to follow step by step, but still I am lacking on some points.
- We had a short chit chat with Ms. Eunseo when the class start at 7 PM this night.

And we were doing some questions for group-task about Javascript. I write it down:

### 1. Differenece between array and array-like object in javascript

- Array is a special variable where you can put several items in it. It uses automatic index with number starting from 0 without any negative.  
It will use square bracket [] and comma to separate other items inside the array.

```js
const my_array = ['item_one','item_two','item_three']
```

- Array-like object is also an object. Before we talk about array-like object, we must know what object is. Object is similar with array, 
but it has flexible index or key name. Object also use parentheses {}.

```js
const my_object = {key_one:'value_one', key_two:'value_two', key_three:'value_three'} 
```

### 2. What is two-way binding?

We can define two-way binding like a strategy to simplify synchronization between JavaScript references and HTML element values and otherwise. 
It means that any change inside the self-property value is reflected inside the value of the HTML element, and any change inside the value of the 
HTML element is propagated back to the self.

- Text Input Example
![image](https://user-images.githubusercontent.com/62550785/197563236-c71b005a-f820-4b7d-a633-1ffda0d10b48.png)
- Just clicked the Update button and you can get teks “New value”
![image](https://user-images.githubusercontent.com/62550785/197563353-91772caa-1e21-42b8-bd86-ca28d298940e.png)

### 3. How the re-rendering is done when using two-way binding

We can synchronization between JavaScript references and HTML element values and otherwise.
As we have already seen, self-property value is reflected inside the value of the HTML element. 
In case self.input = ‘New value’ on text input example we can assume parent component A is input: “assiva@123.com” and then child component B is self.input.
If we analyze the input:“assiva@123.com” is affect the self.input, and if we update the self.input, input: “assiva@123.com” will adjust self.input. 
This is how beautiful thing if we use the two-way binding.

### How do we remove event listener in functional component where you can’t use the lifecycle method?

- As we know, we can use the lifecycle method to unmount or delete something by typing. 

```js
As we know, we can use the lifecycle method to unmount or delete something by typing. 
```

- But if we can’t use the lifecycle method, we can try this function. 

``js
window.removeEventListener();
```

By using the useEffect hook will help remove the EventListener with an optional return value in the callback function. 
Also we can return a function on the useEffect callback and it will run when the component is dissapered(unmount). 
