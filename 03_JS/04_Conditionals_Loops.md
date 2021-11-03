# Conditionals and Loops

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

## Loops
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

