# Functions
Functions are pieces of code written once and called as many times as needed.

Functions require:
- The name of the function (unless it is an anonymous function)
- Parentheses ```()```, which tell javascript that this is a function to run
- An optional list of parameters for the function, enclosed in the parentheses ``()``
- The code to execute when the function runs, enclosed in curly braces ```{}```

```js
addNumbers() {
  let sum = 5
  sum += 6
  console.log(sum)      // 11
}
```
<br>

## First Class Objects
- Functions are First Class Objects in JavaScript
- First Class objects can be:
    - Stored in a variable, Object, or Array
    - Passed as an argument to a function
    - returned from a function

<br>

## Function Definition
```js
function myFunction(parameter1,parameter2){   // ? (the parameter(s) of the function)
    // ? some code to execute goes here
  }

// # Calling a Function
myFunction(argument1,argument2)           // ? the arguments passed to the function
```

<br>

**The following function does not use real numbers.**  
**Instead, it uses parameters.** 
```js
function average(number1, number2) {
  // On line 158 these arguments are "10,16"
    return (number1 + number2) / 2;           // ? add two arguments together, divide sum by 2
  }

  // This function call passes the arguments 10 and 16.
  average(10, 16)                             // 13
```

- when defining a function with parameters, you are declaring those parameters as usable variables within that function.
- ```number1``` and ```number2``` are now variables

<br>

### Sometimes functions do not have included parameters
```js
function testMe(){
  // some code to execute
}

// here are two examples of a function, one without parameters and one with:
function callMe() {
  console.log("Second!");        // "Second!"
  console.log("Third!");         // "Third!"
}

//  ⬇

function callMe(catchyWord) {
  console.log(catchyWord);
    }

callMe("Maybe?");                // Maybe?
```

<br>

**Sometimes funky things can happen:**
```js
// functions return "undefined" by default
function addTwo(num1, num2){
  num1 + num2;
}

console.log(addTwo(1,2));        // undefined
```

**What happened?**
- The function needs to return the value
- Right now if you dropped a debugger below num1 + num2, it would be evident that num1 + num2 is working correctly
- However, without telling js to return the value or assign it to a variable it WILL NOT save the value of this equation

**When using return, keep in mind that nothing PAST return will execute**
```js
function addTwo(num1, num2){
  return num1 + num2;            // ? return the value
}

console.log(addTwo(1,2));        // 3
```

**Returning the value makes the function stop after that line**
```js
function addTwo(num1, num2){
  return num1 + num2;            // ? return the value
  // ! NOTHING will run after this line!
  // ! ANY code after this line simply acts like it does not exist!
}

console.log(addTwo(1,2));        // 3
```

<br>


## Function Expression Syntax
- Functions can be declared using Function Declaration or Function Expression Syntax
- Function Declaration is already familiar:
```js
// * Function Declaration
function newFunction(parameter1,parameter2){
    // some-code
}
```


```js
function sayHello(){
    console.log("hello");
    console.log("bye");
}

++
// * Function Expression
let newFunction = function (parameter1,parameter2){
    // some-code
}
```

```js
let sayHello = function(){
    console.log("Hello Everyone");
}
```

```js
const arr = [getAvg, name, age];

console.log(arr[0](6,4)); // 5
// ? here, we are indexing into the array arr and passing in arguments for function getAvg
```