# Strings, Indexing, and Functions
## Strings
What are Strings?
  - strings represent literal text
  - a string is a sequence of characters surrounded by quotation marks " " or ' '

```js
Examples:
'potato';
"New York";
"amanda@gmail.com";
"Follow the yellow brick road!";
"365 days a year";
"";
" ";
"... ";
```

#### Escape characters with backslash \
```js
"He said, \"what's up?\"";
```
- here, "What's up?" is counted as a string WITH the double quotes. Using \ allows the double quotes (or any symbol escaped) to become a character in a string


#### Why use different quotes?
```js
'Shakespeare wrote, "To be or not to be"';
// for putting quotes or dialouge in strings
"That's a great string";
// for putting apostrephes in strings
```
- Strings must have their opening and closing quotes match
- Strings must not have the same quotes inside them as punctuation:
```js 
'That's a bad string';
```

<br>

### Counting String Length
#### ```.length``` will give you the number of characters in a string:
```js
let ramen = "ramen"
console.log("ramen".length);        // 5
console.log("go home!".length);     // 8
// the spacebar counts as a placeholder and adds towards total length
console.log("".length);             // 0
// an empty string returns 0 for length
```

<br>

### Indexing a String
- Indexes start at 0.
- The index will always be 1 less than the ```.length```
```js
console.log("cat".length);          // 3
console.log("cat"[3]);              // undefined
console.log("cat"[0]);              // 'c'
console.log("cat"[2]);              // 't'

// Examples:
console.log("marigold"[0]);         // 'm'
console.log("marigold"[1]);         // 'a'
console.log("marigold"[2]);         // 'r'
console.log("marigold"[3]);         // 'i'
console.log("marigold"[7]);         // 'd'
console.log("marigold"[10]);        // undefined
console.log("marigold"[-3]);        // undefined
//  if an index number is out of scope (-3, 41 for cat, etc) the REPL returns undefined
```

<br>

### Fun with ```.length``` and ```.indexOf```
```js
console.log("h4xx0r"["h4xx0r".length])
```
- here, you are asking for js to find the length of the string "haxxor" as an index -- but because the index is always one less than the string length, it returns undefined

```js
console.log("h4xx0r"["h4xx0r".length - 1])
```

- here, this will always find the last letter of the string (because the index is always one less than the character count / length)

<br>

### Finding the Indexed Letter
- ```.indexOf``` starts at a beginning of a string checking for characters
- once it finds the character it's looking for it returns and stops executing
```js
console.log("bagel".indexOf("b"));  // 0
console.log("bagel".indexOf("a"));  // 1
console.log("bagel".indexOf("l"));  // 4
console.log("bagel".indexOf("z"));  // -1
// ! if the letter does not exist, -1 will return

// ? what if the letter appears more than once?
console.log("baaaa".indexOf("a"));  // 1
// the indexOf retured will be the first occurrence
```

<br>

### Finding the Indexed Character Snippet
- ```.indexOf``` will return the inxex at the START of the snippet
```js
console.log("door hinge".indexOf("oor"));   // 1
console.log("door hinge".indexOf("hi"));    // 5
console.log("door hinge".indexOf("hint"));  // -1
// if the snippet does not exist, -1 will return
```

<br>

### Concatenating Strings
- Concatenation is joining two strings together
```js
console.log("hello" + "world");             // 'helloworld'
console.log("goodbye" + " " + "moon");      // 'goodbye moon'

let str1 = "hello_"
let str2 = "world"
console.log((str1 + str2).indexOf("worl"))  // 6
```

<br>

## Functions
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

### Function Definition
```js
function myFunction(parameter1,parameter2){   // ? (the parameter(s) of the function)
    // ? some code to execute goes here
  }

// # Calling a Function
myFunction(argument1,argument2)           // ? the arguments passed to the function
```

<br>

#### The following function does not use real numbers.
#### Instead, it uses parameters. 
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

### Sometimes funky things can happen:
```js
// functions return "undefined" by default
function addTwo(num1, num2){
  num1 + num2;
}

console.log(addTwo(1,2));        // undefined
```

###  What happened?
- The function needs to return the value
- Right now if you dropped a debugger below num1 + num2, it would be evident that num1 + num2 is working correctly
- However, without telling js to return the value or assign it to a variable it WILL NOT save the value of this equation

### When using return, keep in mind that nothing PAST return will execute
```js
function addTwo(num1, num2){
  return num1 + num2;            // ? return the value
}

console.log(addTwo(1,2));        // 3
```
- Returning the value makes the function stop after that line
```js
function addTwo(num1, num2){
  return num1 + num2;            // ? return the value
  // ! NOTHING will run after this line!
  // ! ANY code after this line simply acts like it does not exist!
}

console.log(addTwo(1,2));        // 3
```

<br>

## Conditionals
### If Statements
```js
function isItTrue(){
  if (true === true) {           // ? If true true-equals (===) true,
      console.log("true");                           // ? print true
  }
}
```

<br>

### Else Statements
```js
function isItACat(){
  let c = "cat"                       // ? let c represent cat

  if ( c === "dog") {                 // ? if c true-equals dog,
    console.log("I'm a dog!");        // ? print dog
  } else if (c === "turtle") {        // ? or if line 199 doesn't apply, try if c true-equals turtle
    console.log("I'm a turtle!");     // ? and print turtle
  } else if (c === "aardvark") {      // ? or if line 201 doesn't apply, try if c true-equals  aardvark
    console.log("I'm an aardvark!");  // ? print aardvark
  } else {                            // ? or, if NONE of those worked, default to
    console.log("it's a mystery!");   // ? print it's a mystery!
}
```

<br>

## For Loops & While Loops
- For and While loops allow code to be executed indefinitely as long as a condition is met

- For loops are great when you know how many iterations you need (e.g. as many as it takes to get through a list)

- While-loops are great when you have no idea when the iterations will need to stop \ when you want a specific condition to happen and the loop shouldn't stop until then (e.g. until the user finally enters valid input [input validation!] -- or until the user decides to close a menu, etc)

### While Loop
```js
function countUpWhile(){

let index = 0                          // set the variable for the condition being met
                                       // and give it a value
// ! notice that the index variable is initialized /outside/ the while loop
                                       // then write your conditional statement

while (index < 5) {                    // while the variable index is less than 5
  console.log("counting up...")        // print counting up...
  index ++                             // and increment variable index by 1
}
};

countUpWhile();
// this is a classic while loop
// this code will print counting up... 5x before quitting
```

<br>

### For Loop
```js
function countUpFor(){

for (index = 0; index < 5 ; index ++){  // the same logic as while on one line
                                        // set the variable for the condition being met
                                        // and give it a value
                                        // while the variable index is less than 5
                                        // increment variable index by 1
// ! notice that the index variable is initialized /inside/ the for loop
  console.log("counting up...")         // and print counting up...
}
};

countUpFor();
// this is a classic for loop
```

