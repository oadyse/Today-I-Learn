# React Introductory _ S.A (Starting Assignment)

#What is JavaScript object and Immutability?

### JavaScript Object

An object in Javascript is defined as a mutable properties collection, 
which means it is a set of properties (characteristics) that can change their value. 
Javascript objects consist of many properties. Each of these properties is used to describe the object.
Properties can be filled with values of type number, boolean, string, null, and object. 
A property ideally is directly related and clearly describes the object.

### Immutability

In JavaScript, immutability is a data type whose value is fixed. 
Immutable data types are all data types that include primitive types (string, number, boolean, null, undefined, and symbol).

## 1. Primitive type data, and Reference type data

### Primitive Type
Primitive types are the basic types of data such as (byte, short, int, long, float, double, boolean, char). 
They are not objects, and do not have methods. When you declare a primitive data type in JavaScript, it is stored on a stack. 

### Reference Type
Reference types are any instantiable class as well as arrays such as (objects, functions, collections, arrays, dates, other types of object. 
Reference variables store addresses to locations in memory for where the data is stored.

## 2. JavaScript Type Casting(Convertion)

Type casting means conversion of one data type to another explicitly. 
In JavaScript some of the most common methods to convert a datatype to either string using String(), 
to boolean using Boolean(), or to number using Number().

## 3. How to make Immutable Object?

Object immutability is an important concept in any programming language. 
It restricts object modifications and prevents unwanted changes.
We can implement object immutability in JavaScript by using freeze() and seal() methods.

Example :
* Object.freeze() - is used to freeze objects. 
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

* Object.seal() - only protects the objects against adding and removing properties. It allows updating existing properties.
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

## 4. What are shallow copy and deep copy. What are the differences?
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
