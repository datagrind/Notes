# Javascript Basics
## Printing
- use ```console.log();``` to print
```js
"hello"                         // ? Prints nothing.
                                // ? The REPL takes in "hello" but has not recieved
                                // ? instructions to spit anything back out

console.log("hello world");     // hello world
console.log("how are you?");    // how are you?
```

- ```console.log();``` should be used for debugging purposes only.
- Debugging means to locate and solve errors in your code. Console.log is mostly used as a way to locate the error(s) in your code.

<br>

## Operators & Operations
### Operators
```js
()      // parenthesis - encloses an operation and makes it highest priority. 
        // If there are multiple operations enclosed in parenthesis, use Order of Operations to determine priority

%       // ? modulo - divides a number by a number and returns the remainder
*       // multiplication
/       // division
+       // addition
-       // subtraction
```

<br>  

## Order of Operations
**In order of importance, order of operations is:**
```js
() % / * + -

()      // top priority

%       // equal priority to / or *
/       // equal priority to % or *
*       // equal priority to % or /

+       // equal priority to -
-       // equal priority to +

// Examples:

console.log(6 + 4 / (8 % 6) - 6)    // 2

// ? logic:
// ^ (6 + 4 / (8 % 6) - 6)
// (8 % 6) === 2
// ^ (6 + 4 / (2) - 6)
// 4 / 2 === 2
// ^ (6 + 2 - 6)
// 6 + 2 === 8
// ^ (8 - 6)
// 8 - 6 = 2
// expression returns 2
```
<br>

## Boolean Operations
```js
!       // (not)
&&      // (and)
||      // (or)

console.log(!true);     // false
console.log(!false);    // true
console.log(!!false);   // false
```

**The ```&&``` operator only returns true if both sides are true**
```js
console.log(false && false);    // false
console.log(false && true);     // false
console.log(true && false);     // false
console.log(true && true);      // true
```

**the ```||``` operator only returns false if both sides are false**
```js
console.log(false || false);    // false
console.log(false || true);     // true
console.log(true || false);     // true
console.log(true || true);      // true
```

<br>

## De Morgan's Law
**De Morgan's Law distributes bang ! across an expression in parenthesis and flips the boolean operator**
```js
 !(A || B) is equivalent to !A && !B
 !(A && B) is equivalent to !A || !B
```

<br> 

## Comparison Operators
```js
>       // (greater than)
<       // (less than)
>=      // (greater than or equal to)
<=      // (less than or equal to)
==      // ! (DO NOT USE -- will mess up your code)
===     // (deep equals / strict equal to)
!==     // (not equal to)

// Examples:
console.log(10 > 5);            // true
console.log(10 < 5);            // false
console.log(1 < 7);             // true
console.log(7 <= 7);            // true
console.log(5 === 6);           // false
console.log(5 !== 6);           // true
console.log("a" !== "A");       // true
console.log(false === false);   // true

// ! be careful with == vs === ; == is a trap!
// ! always use ===

console.log(5 === "5");         // false
console.log(5 == "5");          // true
console.log(0 === false);       // false
console.log(0 == false);        // true
```

<br>

## Variables

### What is a Variable?
**A variable is a definition set to a value**  
A variable can be thought of as a box with an item inside. The item is the value. 

Variables are Declared and then Initialized.  
Variables that have not been assigned a value return ```undefined```

#### Declaration:
```js
let bootcamp;
// ? let variable bootcamp exist
console.log(bootcamp);      // undefined
```

#### Assignment
```js
// ? The assignment operator = allows a declared variable to be assigned a value

bootcamp = "c0dingz";
// ? let variable bootcamp contain the string value "c0dingz"
console.log(bootcamp);      // 'c0dingz'
// variable bootcamp now holds the value of 'c0dingz'

// You don't need to do both of these things separately
```

#### Initialization
```js
let bootcamp = "c0dingz";
console.log(bootcamp);      // 'c0dingz'

let birthYear = 2012;
console.log(birthYear);     // 2012
```
<br>

## Messing About with Variables
#### Manipulating the value of a variable
```js
let num = 42;
// ? num has the value of 42
console.log(num + 8);   // 50
// ! This only adds 8 to the value of num (42) - It doesn't change the varible
console.log(num);       // 42
// ! The value of num (42) is still 42 because that's what it was initialized as
```

#### How to reassign values to variables
```js
num = num + 10;
// ? num = num (42) + 10
// ? num = new num (52)
console.log(num);       // 52

// Examples
let number = 0;
number += 10;           // equivalent to number = number + 10
number -= 2;            // equivalent to number = number - 2
number /= 4;            // equivalent to number = number / 4
number *= 7;            // equivalent to number = number * 7
console.log(number);    // 14
```

<br>

## NaN
#### NaN refers to Not a Number, a result you get when you are doing bad math
```js
let num;
console.log(num + 3);               // NaN

console.log(undefined + 3);         // NaN
console.log("fish" * 2);            // NaN

// ? NaN is a number type
console.log(typeof Number(NaN));   // number
```

