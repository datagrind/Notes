# Functions and Arrays
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

<br>

## First Class Objects
- Functions are First Class Objects in JavaScript
- First Class objects can be:
    - Stored in a variable, Object, or Array
    - Passed as an argument to a function
    - returned from a function

<br>

## Arrays
### Array Basics
- Arrays are used to store multiple values within a list-like structure
- Values are stored in order and separated by commas
- Arrays are dynamic with no set length - items can be removed or added
- Arrays are global objects - you can make a new array anywhere
```js
let rainbowColors = ["red", "green", "blue"];

rainbowColors[0];                       // red

let newArray = [];                      // ? Arrays can be empty

// Finding the length of an array
[14,42,3].length;                       // 3

[].length;                              // 0

// Arrays can contain many types of data: Strings,Booleans, Integers, other Arrays...
[12, true, "banana", [3]];
```
<br>

### Concatenating Arrays
- Arrays can be concatenated together to form a new, better array
- Arrays must be concatenated into a new, separate array
```js
let array1 = [1, "banana", true];

let array2 = ["snake", [3, 6], false];

let newArray = array1.concat(array2);

console.log(newArray);                   // [1, "banana", true, "snake", [3, 6], false]
```
<br>

### Mutable & Immutable Types
#### Mutable types
- Mutable objects can be changed
- Immutable Objects cannot be changed
- Mutable Types:
    - Arrays
    - Objects

#### Immutable Types
  - Strings
  - Numbers / Integers
  - NaN
  - undefined
  - null

**Some objects (like strings) are re-assignable. THIS DOES NOT MEAN MUTABLE**

<br>

```js
// how to mutate arrays

let arr = ["a", "b", "c"];

arr[1] = "x";                             // mutate array arr at index 1

console.log(arr)                          // ["a", "x", "c"];
```

<br>

## Manipulating Arrays
- Adding elements to an array:
  - When adding array items, multiple items can be added:
  - ```dogs.push(el1, el2, el3)```
  

### Array Methods
### Array.unshift
- Add and element to the start of an array & return the new length
```js
let cats = ["Whiskers", "Mr. Feets", "Snookums"]
let catsLength = cats.unshift("Garfield");
console.log(cats);                          // => ["Garfield", "Whiskers", "Mr. Feets", "Snookums"]
console.log(cats.Length);                   // => 4
```


### Array.push
-  Add an element to the end of an array & return the new length
```js
let animals = ["ant", "bear", "dog"]
let animalLength = animals.push("cat")
console.log(animals);                       // => ["ant", "bear", "dog", "cat"]
console.log(animals.Length);                // => 4
```
<br>

## Removing elements from an array:
- When removing array items, only one item can be removed at at time:
- ```dogs.pop();```
- ```dogs.pop();``` etc.

### Array.shift
-  Remove an element from the start of an array & return the removed element
```js
let cats = ["Paprika", "Whiskers", "Garfield"]
let firstCat = cats.shift();
console.log(cats);                          // => ["Whiskers", "Garfield"]
console.log(firstCat);                      // => "Paprika"
```


### Array.pop
-   Remove an element from the end of a new array & return the removed element
```js
let dogs = ["fido", "rover"]
let lastDog = dogs.pop();
console.log(dogs);                          // => ["fido"]
console.log(lastDog);                       // => "rover"
```

<br>

## Nested Loops
- Basically Loop-Ception
```js
for (let i = 0; i < 4; i++) {               // loop
    for (let j = 0; j < 5; j++) {           // nested loop
      console.log(i, j);
    }
  }
```
- Loops can be nested indefinitely

<br>

## Pairs in Arrays
- How to pair up elements of one array to elements of anotehr array
```js
let dogs = ['belka', 'strelka', 'laika', 'dezik']

for(let i = 0; i < dogs.length; i++) {      // loop
  let dog1 = dogs[i];                       // assign the current i of array dogs to dog1
  for(let j = 0; j < dogs.length; j++) {    // nested loop
    let dog2 = dogs[j]                      // assign the current j of array dogs to dog2
    console.log(dog1, dog2)                 // logs pairs dog1 and dog2
  }
}
```
<br>

## Unique Pairs in Arrays
- How to pair up elements without ever repeating a pair

```js
let dogs = ['belka', 'strelka', 'laika', 'dezik']

for(let i = 0; i < dogs.length; i++) {        // loop
  let dog1 = dogs[i];                         // assign the current i of array dogs to dog1
  for(let j = i + 1; j < dogs.length; j++) {  // nested loop
                                              // ! j = i+1 is needed to keep J one
                                              // ! iteration ahead of i
                                              // ! - this FORCES unique pairs
    let dog2 = dogs[j]                        // assign the current j of array dogs to dog2
    console.log(dog1, dog2)                   // logs pairs dog1 and dog2
  }
}
```
