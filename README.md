# Visit site 
https://annu12340.github.io/Javascript-Notes/

<br/><br/>

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

## Infinities

  ### Positive INFINITY
  
		POSITIVE_INFINITY is displayed when a number exceeds the upper limit of the floating point numbers, which is  "1.797693134862315E+308"
		
		 alert(Math.pow(10, 1000)); /* Infinity */  
		
  ### Negative INFINITY
  
               NEGATIVE_INFINITY is displayed when a number exceeds the lower limit of the floating point numbers, which is "-1.797693134862316E+308".
		
  **POSITIVE_INFINITY** vs. **MAX_VALUE** (or **NEGATIVE_INFINITY** vs. **MIN_VALUE** )
   1. The value of the MAX_VALUE property is the largest number your JavaScript interpreter can             handle. Larger value will be viewed as POSITIVE_INFINITY.
   2. The value of NEGATIVE_INFINITY and POSITIVE_INFINITY are read-only they cannot be changed by
      your scripts; they are returned by JavaScript whenever a function or operation returns a number
      larger than the MAX_VALUE the JavaScript interpreter can handle
		**See the code snippet**
		
         ![Code](https://raw.githubusercontent.com/sumitt1080/demo/master/Capture1.jpg)
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------	 
	 
  The script below illustrate how the JavaScript interpreter understands the concept of infinity (anything out of bound is infinite).

 
 **  alert( Number.NEGATIVE_INFINITY === -2 * Number.MAX_VALUE ); //true**

  The above script return "true" because JavaScript interpreter understands the concept, 
  the negative infinity identical to the negative double of the finite MAX_VALUE property.




### CSS Notes
https://github.com/ResourceAggregator/Frontend-stuff/blob/master/css/css.md
