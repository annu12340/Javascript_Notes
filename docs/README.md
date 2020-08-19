# Index

### Beginner
- let vs var vs const
- Difference between function declaration & function expression
- Primitive data type
- Coercion
- Passing by Value vs. Reference
- Timer function


### Advanced
- Spread operator
- Rest syntax
- Destructuring
- Higher-Order function
- Closures
- call() , apply() and bind()
- hoisting : hoist a flash ie move it to the top
- Currying function
- Event Bubbling and Capturing
- Debugging


<br/>

- Asynchronous js
- JavaScript Design Patterns
- Iterators and generators
- throttle vs debounce
- object creation patterns tutorial - factory , constructor pattern, prototype pattern
- JavaScript ES2020
- Tricky JavaScript interview questions and answers

<hr/>


# Begineer

## 1. let vs var vs const
  - `const` means that the identifier can't be reassigned. But the value can be changed using var and let 
  - let has a block scope while var has function scope. const also has a block scope
  - var has been in js from the beginning and let was introduced recently
![alt text](https://cdn-images-1.medium.com/max/640/1*VVvtcniPdrzrZNEICjYCOg.png)

``` let : l : block and better ```
- var gets hoisted at the top, but variables defined with let doesn't get hoisted

**Example of var:**
```
Input:
console.log(x);
let x=5;
console.log(x);

Output:
Error
```

**Example of let**:
```
Input:
console.log(x);
let x=5;
console.log(x);

Output:
Error
```
In the example below, we get an error because 'let' baz in the second case, has only block scope
```
function run() {
  var foo = "Foo";
  let bar = "Bar";
  console.log(foo, bar);
{
    let baz = "Bazz";
    console.log(baz);
  }
console.log(baz); // ReferenceError
}

run(); 
```

<br/>

## 2. Difference between function declaration & function expression

- Function declaration:

``` function doStuff() {}; ```

- Function expression:

```const doStuff = function() {} ```



- Function declarations are hoisted but function expressions are not.


**Example: Function Expression**

``` alert(foo()); // ERROR! foo wasn't loaded yet ```
```var foo = function() { return 5; } ```

**Example: Function Declaration**

``` alert(foo()); // Alerts 5. Declarations are loaded before any code can run.```
``` function foo() { return 5; } ```

<br/>

## 3. Primitive data type

Following is the list of primitive data types in javascript.
1. Boolean
2. Null
3. Undefined
4. Number
5. BigInt
6. String
7. Symbol

![img](https://cdn-images-1.medium.com/max/640/1*mGcma7XgNq6D7lypiRDrZA.png)

<br/>

## 4. Coercion

When doing mathematical operations, JavaScript can convert numbers to strings:
+ usually adds two numbers. If it is a string, it concatenates them.
- always subtracts. So if a string is given, it is converted to number.
So 2- 'abc' , the output is NaN

**Example**

```
var x = 5 + 7; // x.valueOf() is 12, typeof x is a number

var x = 5 + "7"; // x.valueOf() is 57, typeof x is a string

var x = "5" + 7; // x.valueOf() is 57, typeof x is a string

var x = 5–7; // x.valueOf() is -2, typeof x is a number

var x = 5 - "7"; // x.valueOf() is -2, typeof x is a number

var x = "5" - 7; // x.valueOf() is -2, typeof x is a number

var x = 5 - "x"; // x.valueOf() is NaN, typeof x is a number
```


- Subtracting a string from a string, does not generate an error but returns NaN (Not a Number):

``` 
Example
"Hello" - "Dolly" // returns NaN
```


Example
```
var x = "John"; 
var y = new String("John");
(x === y) // is false because x is a string and y is an object
```

**Example**
```
Boolean('')           // false
Boolean(0)            // false     
Boolean(-0)           // false
Boolean(NaN)          // false
Boolean(null)         // false
Boolean(undefined)    // false
Boolean(false)        // false

Boolean({})             // true
Boolean([])             // true
Boolean(Symbol())       // true
!!Symbol()              // true
Boolean(function() {})  // true
Number(null)                   // 0
Number(undefined)              // NaN
Number(true)                   // 1
Number(false)                  // 0
Number(" 12 ")                 // 12
Number("-12.34")               // -12.34
Number("\n")                   // 0
Number(" 12s ")                // NaN
Number(123)                    // 123
``` 

###### References
1. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness
2. https://medium.com/javascript-in-plain-english/how-type-coercion-in-javascript-works-be723e411c0b
3. https://www.freecodecamp.org/news/js-type-coercion-explained-27ba3d9a2839/

Type Conversions in JavaScript tutorial

1. https://www.youtube.com/watch?v=j9xuvChJftg&list=PL7pEw9n3GkoW5bYOhVAtmJlak3ZK7SaDf&index=53

<br/>

## 5. Passing by Value vs. Reference

![img](https://cdn-images-1.medium.com/max/640/0*aiUhaRomjRzA8_6U.png)

- When assigning a variable (a) a primitive value the equals operator sets up a location (address) in memory (represented by 0x001 in the picture) to store the information and points the variable (a) to that address.

![](https://cdn-images-1.medium.com/max/640/0*5uzUoPoVNxLBxDPF.png)

- Passing by reference relates to objects in Javascript (ALL objects including functions).

In some programming languages, you can actually decide whether something is passed by value or reference, with your code syntax. But in JavaScript you don't have that option. All primitive types are by value, and all objects are by reference.

*Reference*

https://codeburst.io/javascript-passing-by-value-vs-reference-explained-in-plain-english-8d00fd06a47c

<br/>

## 5. Timer function

There are two methods for it:

- setTimeout allows us to run a function once after the interval of time.
- setInterval allows us to run a function repeatedly, starting after the interval of time, then repeating continuously at that interval.

 <hr/>
 
<br/><br/>
<br/>

# Advanced

## 1. Spread operator

spread syntax refers to the use of an ellipsis of three dots ( … ) to expand an iterable object into the list of arguments

```
const foo = ['hello', 'bonjour', 'konnichiwa'];
const bar = [...foo]; 
console.log(bar);
// ['hello', 'bonjour', 'konnichiwa']
```

*Difference between spread and assignment operator*

```
const foo = ['hello', 'bonjour', 'konnichiwa'];
const bar1 = [...foo];
const bar2 = foo;
bar1.push('a');
bar2.push('b');
console.log(foo); //["hello", "bonjour", "konnichiwa", "b"]
console.log(bar1); // ["hello", "bonjour", "konnichiwa", "a"]
console.log(bar2); // ["hello", "bonjour", "konnichiwa", "b"]
```

Arrays and objects are mutable while strings and int are immutable. So, when we write bar2 = foo,  we are using call by reference. Hence, when we edited bar2.push('b'); the value of foo also changed
But using spread operator, we are creating two instances

```
// destrucing in objects
const foo = {
  english: 'hello',
  french: 'bonjour',
  japanese: 'konnichiwa'
};
const bar = {...foo};
console.log(bar);
// { english: 'hello', french: 'bonjour', japanese: 'konnichiwa' }
```

<br/>

## 2. Rest syntax

The rest syntax can also be used to pick up property keys that are not already picked up by the destructuring pattern. Those keys and their values are copied into a new object:

```
let person = {name: "Sarah", country: "Nigeria", job: "Developer" friends: ["Annie", "Becky"]};
let person = {name: "Sarah", country: "Nigeria", job: "Developer" friends: ["Annie", "Becky"]};
let {name, friends, ...others} = person;
console.log(name);//"Sarah"
console.log(friends);//["Annie", "Becky"]
console.log(others);// {country: "Nigeria", job: "Developer"}
```


<br/>

## 3. Destructuring

The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.

1. **Arrays** : We can write any name for the parameter(greeting, prononu) and order is important


```
let introduction = ["Hello", "I" , "am", "Sarah"];
let [greeting, pronoun] = introduction;
console.log(greeting);//"Hello"
console.log(pronoun);//"I"
```

2. **Objects**: Here the parameter name should be equal to the key of the object and order is not important

```
//USUAL MANNER
let person = {name: "Sarah", country: "Nigeria", job: "Developer"};
let name = person.name;
let country = person.country;
let job = person.job;
console.log(name);//"Sarah"
console.log(country);//"Nigeria"
console.log(job);//Developer"


// DESTRUCTURING
let {name, country, job} = person;
console.log(name);//"Sarah"
console.log(country);//"Nigeria"
console.log(job);//Developer"
```

<br/>

## 4. Higher-Order function

A Higher-Order function is a function that receives a function as an argument or returns the function as output.

![](https://i.imgur.com/EqIyF7Em.png)

**a. Map function**

The map() method creates a new array with the results of calling a function for every array element.
The map() method calls the provided function once for each element in an array, in order. It does not change the original array.

```
const arr1 = [1, 2, 3];
const arr2 = arr1.map(item => item * 2);
console.log(arr2);
```


**b. Filter**
```
const persons = [
  { name: 'Peter', age: 16 },
  { name: 'Mark', age: 18 },
  { name: 'John', age: 27 },
  { name: 'Jane', age: 14 },
  { name: 'Tony', age: 24},
];const fullAge = persons.filter(person => person.age >= 18);console.log(fullAge);
```

<br/>

## 5. Closures

A closure is a function having access to the parent scope, even after the parent function has closed.
A Basic Example of Closures in JavaScript:

```
function showName (firstName, lastName) {

var nameIntro = "Your name is ";
    // this inner function has access to the outer 

function's variables, including the parameter

function makeFullName ()   {    
  return nameIntro + firstName + " " + lastName;  
}

return makeFullName ();

}

showName ("Michael", "Jackson"); // Your name is Michael Jackson
```

<br/>

## 6. call() , apply() and bind()

They all attach this into function (or object) and the difference is in the function invocation (see below).

- call attaches this into function and executes the function immediately:
```
var person = {  
  name: "James Smith",
  hello: function(thing) {
    console.log(this.name + " says hello " + thing);
  }
}
person.hello("world");  // output: "James Smith says hello world"
person.hello.call({ name: "Jim Smith" }, "world"); // output: "Jim Smith says hello world"
```

- bind attaches this into function and it needs to be invoked separately like this:

```
var person = {  
  name: "James Smith",
  hello: function(thing) {
    console.log(this.name + " says hello " + thing);
  }
}

person.hello("world");  // output: "James Smith says hello world"

var helloFunc = person.hello.bind({ name: "Jim Smith" });

helloFunc("world");  // output: Jim Smith says hello world"
```

or like this:

```
var helloFunc = person.hello.bind({ name: "Jim Smith" }, "world");
helloFunc();  // output: Jim Smith says hello world"
```

- apply is similar to call except that it takes an array-like object instead of listing the arguments out one at a time:

```
function personContainer() {

  var person = {  
     name: "James Smith",
     hello: function() {
       console.log(this.name + " says hello " + arguments[1]);
     }
  }
  person.hello.apply(person, arguments);
}

personContainer("world", "mars"); // output: "James Smith says hello mars", note: arguments[

```

<br/>
1. You can use call()/apply() to invoke the function immediately. bind() returns a bound function that, when executed later, will have the correct context ("this") for calling the original function. So bind() can be used when the function needs to be called later in certain events when it's useful.


2. Note that when using the apply() function the parameter must be placed in an array. Call() accepts both an array of parameters and a parameter itself.

```
const greetingJohn = greeting.bind(john, 'uk');
greetingJohn();//must be called again
greeting.call(person,'India');
greeting.apply(person,['India']);// has an array
```


**Refernce**

https://medium.com/r?url=https%3A%2F%2Fcodesquery.com%2Fjavascript-call-apply-bind-method%2F

<br/>

## 7. Hoisting : hoist a flash ie move it to the top

Hoisting is JavaScript's default behavior of moving declarations to the top.In JavaScript, a variable can be declared after it has been used.In other words; a variable can be used before it has been declared


<br/>

## 8. Currying function

- Currying is a transformation of functions that translates a function from callable as f(a, b, c) into callable as f(a)(b)(c).

Currying is when you break down a function that takes multiple arguments into a series of functions that each take only one argument. Here's an example in JavaScript:

```
function add (a, b) {
  return a + b;
}
add(3, 4); // returns 7
```

This is a function that takes two arguments, a and b, and returns their sum. We will now curry this function:

```
function add (a) {
  return function (b) {
    return a + b;
  }
}
```

This is a function that takes one argument, a, and returns a function that takes another argument, b, and that function returns their sum.

```
add(3)(4);
var add3 = add(3);
add3(4);
```

The first statement returns 7, like the add(3, 4) statement. The second statement defines a new function called add3 that will add 3 to its argument. This is what some people may call a closure. The third statement uses the add3 operation to add 3 to 4, again producing 7 as a result.



<br/>

## 9. Event Bubbling and Capturing

Event bubbling and capturing are two ways of event propagation in the HTML DOM API, when an event occurs in an element inside another element, and both elements have registered a handle for that event.

![](https://cdn-images-1.medium.com/max/480/0*Fk8I6Pmm5WOS4SXI.png)

With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.
With capturing, the event is first captured by the outermost element and propagated to the inner elements.

<br/>

## 10. Debugging

https://www.youtube.com/watch?v=-bS6u_oQFtc&list=PL7pEw9n3GkoW5bYOhVAtmJlak3ZK7SaDf&index=29


<br/> <br/>

## 11. Asynchronous js

1. Callback function
2. Promises
3. Async await

JavaScript is synchronous by default and is single threaded. This means that code cannot create new threads and run in parallel. JavaScript introduced several features that help us with asynchronous code that do not involve using callbacks:

**Reference**
- https://flaviocopes.com/javascript-promises/
- https://flaviocopes.com/javascript-async-await/
- https://www.youtube.com/watch?v=IGoAdn-e5II


## 12. JavaScript Design Patterns

https://medium.com/better-programming/javascript-design-patterns-25f0faaaa15


## 13. Iterators and generators

Iterators are a new way to loop over any collection in JavaScript.

https://codeburst.io/a-simple-guide-to-es6-iterators-in-javascript-with-examples-189d052c3d8e

<br/>

## 14. Throttle vs debounce

Throttling and debouncing are two ways to optimize event handling.

![](https://cdn-images-1.medium.com/max/640/1*8myBvrcAJu1h0YfhWfX7qg.png)

- Debouncing enforces that a function not be called again until a certain amount of time has passed without it being called. As in "execute this function only if 100 milliseconds have passed without it being called."

- Throttling enforces a maximum number of times a function can be called over time. As in "execute this function at most once every 100 milliseconds."


*Good demo (codepen)*
https://css-tricks.com/the-difference-between-throttling-and-debouncing/


<br/>

## 15. Object creation patterns tutorial 

https://www.youtube.com/watch?v=xizFJHKHdHw&list=PL7pEw9n3GkoW5bYOhVAtmJlak3ZK7SaDf&index=5

JavaScript has a multitude of styles for creating objects

#### 1. Object Literals

```
var o = {
  x: 42,
  y: 3.14,
  f: function() {},
  g: function() {}
};
```

#### 2. Factory Functions
This is the absolute simplest way to create a family of objects that share the same structure, interface, and implementation. Rather than creating an object literal directly, instead we return an object literal from a function. This way, if we need to create the same type of object multiple times or in multiple places, we only need to invoke a function:

```
function thing() {
  return {
    x: 42,
    y: 3.14,
    f: function() {},
    g: function() {}
  };
}
var o = thing();
```

**Reference**

- https://www.sitepoint.com/javascript-object-creation-patterns-best-practises/
- https://www.javascripttutorial.net/create-objects-in-javascript/

- https://medium.com/r?url=https%3A%2F%2Fwww.dofactory.com%2Fjavascript%2Fdesign-patterns
- https://www.dofactory.com/javascript/design-patterns

<br/>

## 16. JavaScript ES2020

The new JavaScript features in ES2020 are:

➡️ String.prototype.matchAll

➡️ import()

➡️ BigInt

➡️ Promise.allSettled

➡️ globalThis

➡️ for-in mechanics

➡️ Optional Chaining

➡️ Nullish coalescing Operator

*Reference*
- https://radiant-brushlands-42789.herokuapp.com/medium.com/better-programming/javascript-es2020-features-with-simple-examples-d301dbef2c37 
- https://www.freecodecamp.org/news/javascript-new-features-es2020/

<br/> <br/>  <br/>


# Tricky JavaScript interview questions and answers

**Find output:**

a. console.log(5<6<7)
b. console.log(5>6>7)

a. console.log(5<6<7) =console.log(true<7)=true
b. console.log(5>6>7) =console.log(true>7)=false


<br/>

**Video**

- https://www.youtube.com/watch?v=QCQVttjblRs&list=PL7pEw9n3GkoWn5TcqAdmSzXcvC3d_tfAh&index=5

- Tricky JavaScript Interview Questions and Answers https://www.youtube.com/watch?v=qsNxdukPc2U&list=PL7pEw9n3GkoWn5TcqAdmSzXcvC3d_tfAh&index=6

- JavaScript Mock Interview https://www.youtube.com/watch?v=OOC-ypVnHAY&list=PL7pEw9n3GkoWn5TcqAdmSzXcvC3d_tfAh&index=12
