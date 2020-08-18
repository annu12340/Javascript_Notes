# Index

#### Begineer
- let vs var vs const
- difference between function declaration & function expression
- Primitive data type
- coercion

#### Advanced


<hr/>


#### Begineer
  ##### let vs var vs const
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


  ##### Difference between function declaration & function expression
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


### Primitive data type
Following is the list of primitive data types in javascript.
1. Boolean
2. Null
3. Undefined
4. Number
5. BigInt
6. String
7. Symbol
 ![img](https://cdn-images-1.medium.com/max/640/1*mGcma7XgNq6D7lypiRDrZA.png)


### coercion
When doing mathematical operations, JavaScript can convert numbers to strings:
+ usually adds two numbers. If it is a string, it concatenates them.
- always subtracts. So if a string is given, it is converted to number.
So 2- 'abc' , the output is NaN

**Example**
var x = 5 + 7; // x.valueOf() is 12, typeof x is a number
var x = 5 + "7"; // x.valueOf() is 57, typeof x is a string
var x = "5" + 7; // x.valueOf() is 57, typeof x is a string
var x = 5–7; // x.valueOf() is -2, typeof x is a number
var x = 5 - "7"; // x.valueOf() is -2, typeof x is a number
var x = "5" - 7; // x.valueOf() is -2, typeof x is a number
var x = 5 - "x"; // x.valueOf() is NaN, typeof x is a number


Subtracting a string from a string, does not generate an error but returns NaN (Not a Number):
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

##### References
1. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness
2. https://medium.com/javascript-in-plain-english/how-type-coercion-in-javascript-works-be723e411c0b
3. https://www.freecodecamp.org/news/js-type-coercion-explained-27ba3d9a2839/

