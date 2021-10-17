# Array Javascript methods
## ```forEach();```
**```forEach();``` is a built in array method in JS that iterates through an array in order and can return the element, index, and the array itself**

```js
// ? have an array:
let parks = ["Zion", "Yellowstone", "Yosemite", "Valley of Fire"]

// ? Remember this iterating for loop?
for(let i =0; i< parks.length; i++){
}

// ? Enter: JS forEach() method!
parks.forEach(function(park) {            // => Here, the parameter is the element of the array starting at [0]
    console.log(park);
});                                       // => closing forEach(); parenthesis goes OUTSIDE curly brace
```

- ```forEach()```; can take in more than just the parameter for array elements!
- The parameters accepted are positional - they will ALWAYS accept (ele, index, array) in that order
- ```forEach()```; will only iterate through an array in order (L=>R) hitting every element along the way

```js
parks.forEach(function(ele, i, array) {
     // ? Here, the parameters are, in order:
      // ? the element (starting at [0])
      // => the index of that element (starting at [0])
      // => the array itself

    console.log(ele);                              // => Zion
    console.log(i);                                // => 0
    console.log(array);                            // => ["Zion", "Yellowstone", "Yosemite", "Valley of Fire"]
});
```

- Because the parameters of ```forEach();``` are positional, if you just wanted the index of the element you would still need to pass in a parameter for the element to get to the index:

```js
parks.forEach(function(ele, i) {                   // => to get to the i parameter you have to pass in
                                                   // an element parameter first
    console.log(i);                                // => 0
});
```

- Do not return inside a ```forEach();``` -- it does not work with a return statement inside it.
- The return value of ```forEach();``` is always undefined.

<br>

## ```Map();```
**```map();``` is a built in array method in JS that generates a new array and pushes elements from the previous array to the new array**
```js
// have an array:
let parks = ["Zion", "Yellowstone", "Yosemite", "Valley of Fire"]

// old method to uppercase all letters of the strings in an array:
let newParks = [];
for(let i =0; i< parks.length; i++){
    let currentPark = parks[i];
    newParks.push(currentPark.toUpperCase());
}
console.log(newParks);

// Enter: JS map() method!
let newParks = parks.map(function(park){
    return park.toUpperCase();
});
console.log(newParks)                               // => ["ZION", "YELLOWSTONE", "YOSEMITE", "VALLEY OF FIRE"]
```
- The parameters accepted are positional - they will ALWAYS accept (ele, index, array) in that order
- ```map();``` will only iterate through an array in order (L=>R) hitting every element along the way

**You MUST return inside ```map();``` -- it is expecting a return statement to work properly**

<br>

## ```filter();```
**```filter();``` pushes an element to a new array if the result of some boolean logic for that element is true**
```js
// have an array:
let parks = ["Zion", "Yellowstone", "Yosemite", "Valley of Fire"]

// old method to filter parks that start with Y:
let yParks = [];
for (let i = 0; i <parks.length; i++){
    let park = parks[i];
    if (park[0] === 'Y'){
        yParks.push(park);
    }
}
console.log(yParks);

// Enter: JS filter() method
parks.filter(function(park){
    return park[0] === 'Y';
});
```

- The parameters accepted are positional - they will ALWAYS accept (ele, index, array) in that order
- ```filter();``` will only iterate through an array in order (L=>R) hitting every element along the way

**You MUST return inside ```filter();``` -- it is expecting a return statement to work properly**

<br>

## ```reduce();```
**```reduce();``` sums up all the elements in an array into the sum of those elements**

```js
// how to use reduce();
let nums = [3, 7, 5, 9]

nums.reduce(function(accum, el){
 // => reduce(); has the parameters accumulator & element built into its function
    return accum + el;                              // => 24 (3+7+5+9)
});
```

- Accumulator starts at [0] and adds the el ([1],[2], etc.) to the accumulator

- The parameters accepted are positional - they will ALWAYS accept (accum, num) in that order
- ```reduce();``` will only iterate through an array in order (L=>R) hitting every element along the way
