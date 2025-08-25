### 1. Function Expression
Anonymous or named function assigned to a variable.  
```js
const greet = function() { console.log("Hi!"); };
```  
### 2. Arrow Function
Concise syntax, does not bind `this` keyword.  
```javascript
()=>{}
// Or
parameter => return; // if only one parameter & no body with only return statement
```  
#### Example  
```javascript
() => {console.log("Hello!")}
```  
```javascript
() => console.log("Hello!");
```  
```javascript
a => {return a*2;}
// Or
a => return a*2;
// const doubler = a => a*2;
```  
### 3. Anonymous Function  
Function without a name, often used inline.
```javascript
setTimeout(function() { console.log("Done!"); }, 1000);
```  
### 4. Named Function
Function with a specific name for recursion/debugging.  
```javascript
const greet = function hello() { 
  console.log("Hi!"); 
};
```  
### 5. Constructor Function  
Used to create objects instance out of class using `new` keyword.
```javascript
// actual constructor function 
function Person(name) { 
  this.name = name; 
}
```  
#### example
```javascript
// created instance by invoking constructor by using new keyword
let p1 = new Person("Arjun");  
```  
### 6. Async Function
Handles asynchronous code with await.
```javascript
async function fetchData() { 
  await getData(); 
}
```  
### 7. IIFE (Immediately Invoked Function Expression)
Executes immediately after defining & get discarded from memory.  
```javascript
(function() { 
  console.log("Run now!"); 
})();
```  
### 8. Callback Function
A function passed as an argument to another function and executed later.  
```javascript
setTimeout(() => console.log("Callback!"), 1000);
```  
### 9. Higher-Order Function (HOF)
Takes another function as an argument or returns a function.
```javascript
const hof = (fn) => fn();
hof(() => console.log("HOF!"));
```  