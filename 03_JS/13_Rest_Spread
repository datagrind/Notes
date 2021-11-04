## Rest and Spread Operators

The Rest and Spread operators use the same exact operator, ```...```, but in very different scenarios

## Rest
The Rest operator accesses a data structure allowing access to all elements.

**Rest is always used in parameters**

```js
function colorPicker(color, ...otherColors){      // ... allows access to all other elements passed in as an array
    console.log(otherColors)                      // [blue, yellow]
}

console.log(colorPicker("red", "blue", "Yellow"));
```
<br>

```js
function colorPicker(color, ...otherColors){ 
    let string = "I picked the colors: " + color  // "I picked the colors red" 
    otherColors.forEach(function(arg){
        string = string + ", " + arg;
    });
    return string                                 // "I picked the colors red, blue, yellow"          
}                        

console.log(colorPicker("red", "blue", "yellow"));
```
<br>

## Spread
The spread operator takes in parameters and puts them into a single array

### Array Usage
```js
let arr1 = [1, 2, 3, 4, 5]
let arr2 = [8, 9, 10, 11, 12]

let arr3 = [...arr1, ...arr2]

console.log(arr3);                  // [1, 2, 3, 4, 5, 8, 9, 10, 11, 12]
```
### Object Usage:
```js
let obj1 = {name: "benny"};
let obj2 = {animal: "bear", game: "Stardew Valley"};
let obj3 = {obj1, obj2, movie: "Snatch"}

        // {obj1: {name: "benny"}, obj2: {animal: "bear", game: "Stardew Valley"}, movie: "snatch" }
let obj4 = {...obj1, ...obj2, movie: "snatch"}
        // {name: "benny", animal: "bear", game: "Stardew Valley", movie: "snatch" }
```