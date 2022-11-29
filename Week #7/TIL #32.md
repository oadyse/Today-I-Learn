# Today-I-Learn #32
## SpartaCodingClub Full-Stack Bootcamp in Indonesia
November 29th, 2022
  
## 🔐 1. What role do ORM like Sequelize, and Database like MySQL have respectively?

**Sequelize** is an Object Relational Mapper for Node. js. Sequelize lets us connect to a database and perform operations without writing raw SQL queries
. It abstracts SQL queries and makes it easier to interact with database models as objects.

MySQL is a tool used ***to manage databases and servers***
, so while it's not a database, it's widely used in relation to managing and organising data in databases.

## 🔐 2. The router for express.js is middleware. What is the principle behind implementing the router with the middleware?

Why do we use middleware?

- Middleware can executes any code
- We can make changes to the request-response objects
- Middleware can also End the request-response cycle
- Middleware can call the next middleware function in a stack

> We use these functions to modify our middleware to perform many tasks. ***If we want to block our site for some country or if we're going to check the authentication of a user etc., we use middleware for that.***
> 

Implementing a middleware application allows developers to integrate operating systems and hardware with the wide variety of various applications that are currently available. 

> ***Simply put, middleware is built to connect one set of code to another set of code, and without this tech, our digital landscape would be very different from what we know it.***
> 

<aside>
🔐 How does require function - that is used for refactoring in Node.js and fetches the downloaded module through npm - works? Find a connection with IIFE to find and summarise.

</aside>

Node.js follows the CommonJS module system, and the built-in require function is the easiest way to include modules that exist in separate files. The basic functionality of require is that it reads a JavaScript file, executes the file, and then proceeds to return the exports object.

> **Nodejs is a wrapper with five arguments.**
> 

Nodejs wraps your .js files with an immediately invoked function expression (IIFE). The IIFE has five arguments: `exports`, `require`, `module`, `__filename`, and `__dirname`.

# DIY Section

<aside>
🔑 Q1. What is try and catch error handling? Give an example structure of this code

</aside>

Try..catch is one of exception handling syntax to catch the error by running test code. Try-catch works only for runnable codes. That is, it works in the valid JavaScript. he errors, occurring in the reading phase are known as “parse-time” errors. They are unrecoverable as the engine doesn’t understand the code. 

The code structure :

```jsx
try {
  console.log('Start test runs'); 
  anyVar; // error, variable isn't defined
  console.log('End of test (never reached)'); 
} catch (err) {
  console.log(`Error has occurred`); 
}
```

<aside>
🔑 Q2. What’s the constructor?

</aside>

A method defined by `constructor()` inside a class is called a “**constructor**”. This method is called inside Javascript when an **instance** is created based on a predefined class.

Example:

```jsx
class User {
	constructor(name, age, tech) { // Constructor for User class
	[this.name](http://this.name/) = name;
	this.age = age;
	this.tech = tech;
	}
}

const user = new User("James Park", 28, "Node.js"); // create user instance

console.log([user.name](http://user.name/)); // James Park
console.log(user.age); // 28
console.log(user.tech); // Node.js
```

<aside>
🔑 Q3. What’s the inheritance?

</aside>

An instance of a class inherits **all** of the functionality of the class it declares. Inheritance can be used to divide a class into a **parent class** and a **child class**. In the case of the parent class, information such as methods and internal variables can be assigned to the child class.

Example:

```jsx
class User { // User parent class
	constructor(name, age, tech) { // parent class constructor
	[this.name](http://this.name/) = name;
	this.age = age;
	this.tech = tech;
	}
	getTech(){ return this.tech; } // parent class getTech method
}

class Employee extends User{ // Employee child class
	constructor(name, age, tech) { // child class constructor
	super(name, age, tech);
	}
}

const employee = new Employee("James Park", "28", "Node.js");
console.log([employee.name](http://employee.name/)); // James Park
console.log(employee.age); // 28
console.log(employee.getTech()); // Call the parent class's getTech method: Node.js
```

<aside>
🔑 Q4. What is the role of Middleware?

</aside>

Middleware is software that enables one or more kinds of communication or connectivity between two or more applications or application components in a distributed network. It manages the request, response and next method between client and web server. In distributed system middleware has benefit in administrative things. The benefits are :

- Middleware used in distributed systems to provide common services, such as authentication, authorization, compilation for best performance on particular architectures, input/output translation, and error handling.
- Middleware can be modularized from the application so it has better potential for reuse with other applications running on different platforms.
- Application developers can design Middleware that it becomes independent of specific hardware environments or operating system platforms which simplifies porting applications developed on one type of platform onto another without rewriting code or without resorting to inefficient and expensive binary compatibility toolsets such as cross-compilers.

<aside>
🔑 Q5. What is JWT and what is used for?

</aside>

JSON Web Token (JWT) is **an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object**
. This information can be verified and trusted because it is digitally signed.

JWT is used for information exchange. JWTs are a good way of **securely transmitting information between parties because they can be signed**
, which means you can be sure that the senders are who they say they are. Additionally, the structure of a JWT allows you to verify that the content hasn't been tampered with.
