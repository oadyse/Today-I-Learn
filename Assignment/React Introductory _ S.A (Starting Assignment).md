# React Introductory _ S.A (Starting Assignment)

## What are the characteristics of JavaScript - data type and JavaScript?

#### Javascript has several characteristics such as:
- **A dynamic scripting language**

Dynamic scripting language here means that javascript has the ability to respond to an input from a user that comes from an event and is responded directly without going through the web server.
*The event was occurred at the time of pressing the mouse button, pressing the button and others.*

- **Javascript is a cross-platform language**
    
Javascript can be accessed in any browser and we can execute correctly as long as the browser supports javascript as well and can run the browser on the computer.

- **Data type**

The data types in JavaScript are similar to other programming languages such as Java or C#.

### 1. Loosely typed dynamic language

Loosely typed dynamic language means that JavaScript is a dynamic and loosely typed language. JavaScript allows the user to not have specify the type of variable to be created, variables in JavaScript can allow any type of value, such as:

```js
<!DOCTYPE html>
<html>
<body>
	<h1>Example JavaScript Variables</h1>
	
	<p id="p1"></p>
	<p id="p2"></p>
	<p id="p3"></p>
	<p id="p4"></p>
	<p id="p5"></p>

	<script>
		var variable = 1;  // numeric value (this syntax will result "1")
		document.getElementById("p1").textContent = variable;

		variable = 'one'; // string value (this syntax will result "one")
		document.getElementById("p2").textContent = variable;

		variable = 1.1; // decimal value (this syntax will result "1.1")
		document.getElementById("p3").textContent = variable;

		variable = true; // Boolean value (this syntax will result "true")
		document.getElementById("p4").textContent = variable;

		variable = null; // null value (this syntax will result "null value")
		document.getElementById("p5").textContent = variable;
    </script>
</body>
</html>
```

### 2. JavaScript Type Casting

In JavaScript, typecasting means converting one data type to another data type by converting a string data type to a Boolean or converting an integer data type to a string data type. Typecasting in JavaScript is known as type conversion or type coercion, there are two types of casting in JavaScript, such as **Implicit type casting** and **explicit type casting**.

- **Implicit type casting** is a data type conversion performed due to internal requirements or automatic conversion by the compiler or interpreter.
- **Explicit type casting** is done forcibly by the developer in order for the lines of code to look good. In JavaScript type casting can be done only for strings, numbers and Boolean data types (objects).

## What is JavaScript object and Immutability?

#### JavaScript Object

*An object in Javascript is defined as a mutable properties collection, 
which means it is a set of properties (characteristics) that can change their value*. 
Javascript objects consist of many properties. Each of these properties is used to describe the object.
Properties can be filled with values of type number, boolean, string, null, and object. 
A property ideally is directly related and clearly describes the object.

#### Immutability

In JavaScript, *immutability is a data type whose value is fixed*. 
Immutable data types are all data types that include primitive types (string, number, boolean, null, undefined, and symbol).

### 1. Primitive type data, and Reference type data

#### Primitive Type
**Primitive types** are the basic types of data such as (byte, short, int, long, float, double, boolean, char). 
They are not objects, and do not have methods. When you declare a primitive data type in JavaScript, it is stored on a stack. 

#### Reference Type
**Reference types** are any instantiable class as well as arrays such as (objects, functions, collections, arrays, dates, other types of object. Reference variables store addresses to locations in memory for where the data is stored.

### 2. JavaScript Type Casting(Convertion)

*Type casting means conversion of one data type to another explicitly.* 
In JavaScript some of the most common methods to convert a datatype to either string using String(), 
to boolean using Boolean(), or to number using Number().

### 3. How to make Immutable Object?

Object immutability is an important concept in any programming language. 
It restricts object modifications and prevents unwanted changes.
We can implement object immutability in JavaScript by using freeze() and seal() methods.

Example :
* **Object.freeze()** - *is used to freeze objects.* 
So, if you want an object to be protected from changes, you can pass it to the freeze() method as follows. And it will return an immutable version of that object.

```js
var draftArticle = { 
   name: “Object Immutability”, 
   author: “Chameera Dulanga”, 
   publication: “Bits and Pieces”, 
   status: “In review”
};
var publishedArticle = Object.freeze(draftArticle);
```

* **Object.seal()** - only protects the objects against adding and removing properties. It allows updating existing properties.
```js
var article = { 
   name: “Object Immutability”, 
   author: “Chameera Dulanga”, 
   publication: “Bits and Pieces”, 
   status: “In review”
};
// Sealing the object
Object.seal(article);
```

### 4. What are shallow copy and deep copy. What are the differences?
* What is Shallow copy?
A bitwise copy of an object, where a new object is created and it has the same copy 
of the values in the original object, is called a Shallow copy. If any of the object 
fields refer to the other object then in such cases only the reference address is copied.

* What is Deep copy?
When the process of copying occurs repetitively and a copy of the object is always 
copied in another object, then it is called deep copy. In this process, initially, 
a new collection of the object is constructed, and then the copies of the child object 
frequently populate those found in the original.

* Difference between Shallow copy and Deep copy

| Shallow Copy | Deep Copy |
| ----------- | --------- |
| In Shallow copy, a copy of the original object is stored and only the reference address is finally copied.	| In Deep copy, the copy of the original object and the repetitive copies both are stored. |
| Shallow copy is faster than Deep copy.	| Deep copy is slower than Shallow copy. |
| The changes made in the copied object also reflect the original object.	| There is no reflection on the original object when the changes are made in the copied object. |
| It stores references of the object in the main memory.	| It stores copies of the object values. |


## What would be the “b” value printed on the console?

![image](https://user-images.githubusercontent.com/62550785/197227507-8a9ebe80-4d8d-437d-a885-1b9e0f83d58f.png)

Variable “**b**” will be printed as 1 in *console.log* as it was assigned. There are 3 console lines that print “**b**”.

### 1. Which “b” value would be printed from which line of console.log? Explain why.

**based on my text editor, it was : line 10, line 7, and line 13**
**line 10** : printed as 1 because the variable “b” is assigned as 1
**line 7** : printed as 101 because there is an incrementation (b++) in the function hi(), and it’s going to adding 1 to the variable b when the function is called
**line 13** : printed as 1 because the variable “b” was declared as 1 before the hi() function was created.

### 2. What would be //console.log(a); in the comment? If there’s an error, explain why and fix the error.

![image](https://user-images.githubusercontent.com/62550785/197228826-c4a17739-3468-4196-a44d-8aa884f33cbb.png)

For the error part, “**a**” is a **constant** with a value is **1**, which is defined and declare in the **hi()** function, so the constant “**a**” has a limited scope in the **hi()** function. That’s why the console give an alert *‘a is not defined’*.

The way to fix this easily is turn **const** a into global scope variable by replace it to outside of the **hi()** function and **const** a is already global scope variable then you can access it from anywhere.

![image](https://user-images.githubusercontent.com/62550785/197229743-24edc714-bee0-487a-bca5-2e39be88fe28.png)
