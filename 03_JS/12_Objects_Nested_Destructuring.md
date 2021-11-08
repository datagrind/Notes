# Objects and Nested Destructuring

An object is a data structure that stores other data. Objects are used to store multiple **key value pairs**
- Keys are unique strings
 - Values can be anything (string, other object, etc)
- Order is not guaranteed!
- Objects are indexed using keys. 
- You **CANNOT** use ```[i]``` indexing on an object, key-value pairs **DO NOT HAVE RELIABLE POSITIONING** inside
<br>

**[Nested Destructuring](#nested-destructuring)** refers to getting at the data of an object nested inside another object
<br>

## Value vs. Reference Data Types
### Reference Data Type:
- Object
   - An Array is also a type of object

### Value (primitive) Data Types:
- Primitive / Value Data Types are Immutable
- Boolean - True and False
- Null - represents the intentional abscence of a value
- Undefined - default return value for many things in JS
- Number - integers / numbers
- String - ordered collection of characters ('apple')

```js
/// Value types
let acorns = 25
let apples = acorns
```


<br>

## Objects
### Empty object
```js
let testObject = {};        // Empty JS Objects are undefined
```


**Trying to access a key that does not exist returns undefined**

```js
testObject[0] === undefined // undefined
```

**Check if a key value pair is not undefined (ie it exists)**
```js
testObject[0] !== undefined // if testObject at key [0] is undefined...
```

<br>

## Ordered vs. Unordered
**Arrays are ordered, Objects are unordered**
```js
let arr = [0,1,2,3];        // arrays have indices (arr[1]) & elements (arr[1] === 1)

let obj = {name: 'Mylo', age: 1000};   // objects have keys (name) and values ('Mylo')
console.log(obj);                      // {age: 1000, name: 'Mylo'}
```
<br>

## Object Assignment
**In array assignment, you can use indices to reassign array elements**
```js
let arr = [0,1,2,3];

arr[2] = 4                  // reassign the element at arr[2] to 4
console.log(arr)            // [0,1,4,3]
```
**In object assignment, you can use dot or bracket notation to reassign (but dot is more common)**
 ```js
let obj = {name: 'Mylo', age: 1000};

obj.name = 'Warren'         // reassign the value for key name to 'Warren'
console.log(obj)            // {name: 'Warren', age: 1000}

obj.taco = 'al pastor'      // assign new key taco to new value 'al pastor'
console.log(obj)            // {name: 'Warren', age: 1000, taco: 'al pastor'}
```
**another example:**
 ```js
let story = {
    beginning: "Once upon a time...",
    end: "And they lived happily ever after",
};                          // an object broken up on different lines

let makeAStory = function (){
    console.log(story);
    // print the story so far
    if (story.middle === undefined) {
        // if there is no middle key
        story.middle = 'drama';
        // add key middle with value 'drama'
        console.log('added middle');
        // print that the function added middle
} else {
        console.log('story complete')
        // print that the story is complete (there was already a key middle)
    }
};
makeAStory();               // added story
makeAStory();               // story complete
```


**another example:**
```js
let Biff = {
    type: 'dog',
    age: 10,
};                          // Object Biff with key-value type: 'dog' and age: 10

let Buster = Biff           // let variable Buster point to Object Biff

Buster.age = 0              // set the key age at Buster (which references Biff) to Value 0

console.log(Biff, Buster);  // { type: 'dog', age: 0 } { type: 'dog', age: 0 }
```

<br>

## Dot Notation vs Bracket Notation
- Dot and bracket notation both allow you to set and access keys in an object
- Bracket notation will allow you to use variables for setting a key!
let obj = {};


```js
console.log(obj.name)       // get Obj at name key (which is a string literal)
console.log(obj['name'])    // get Obj at string literal 'name' key (must specify the string if not a variable)
```

### Bracket Notation
```js
testObject["num"] = 10;     // testObject key num has value of 10
```
```js
let string = "yay";
obj[string] = "yay!";
```

**Object keys in bracket notation are looking for a variable**
```js
let obj = {name: 'Mylo'};

console.log(obj[name])          // when using bracket notation, JS expects a variable
console.log(obj['name'])        // If using a literal key string you must specify it is a string
```

### Dot Notation

```js
testObject.num2 = 20;       // testObject key num2 has value of 20
```
```js
let obj = {food: 'Taco'}

let thingToCheck = food

console.log(obj[thingToCheck])
// find the variable thingToCheck, which is assigned to the key food
console.log(obj.thingToCheck)
// returns undefined - dot notation cannot look for variables
```

Objects cannot exist without keys and keys cannot exist without objects.  
**They are PAIRS**

<br>

## Destructuring
You can destructure both Arrays and Objects

### Array Destructuring
```js
arr = [Taylor, 21, AZ]

let name = arr[0]
let age = arr[1]

console.log(name);                  // prints Taylor
console.log(age);                   // 21

// ! IS THE SAME AS

arr = [Taylor, 21, AZ]

let [name, age, location] = arr
                                    // this is destructuring

console.log(name)                   // prints Taylor
console.log(location)               // prints Az
```

### Object Destructuring
```js
let object = {name: Dillon, age: 19, job: mechanic}

console.log(object.name)            // prints Dillon
console.log(object["name"])          // prints Dillon
```


**To destructure:**
```js
let {name, age, job,} = object      // let these names be KEYS in the object
```
**The keys inside the ```{ }``` are now VARIABLES THAT CAN BE CALLED**
```js
console.log(name)                   // Dillon
console.log(age)                    // 19
```

If you have destructured the object you call JUST the variable name. That variable will return the **VALUE** associated with the **KEY** it is assigned to

<br>

**Objects have NO order, so:**
```js
let {name, age, job,} = object
```
- name is assigned to whatever is the FIRST key in the object
- age is second key etc.

<br>

## Aliasing
### Renaming keys in destructuring
**To rename a key:**
```js
let object = {name: Dillon, age: 19, job: mechanic}

let {name:firstN, age, job } = object
```
reassign name to firstN, let that hold the value of the first key in the object and let age hold the value of age and let job hold the value of job

- the reassignment character for objects is :
- the reassignment character for let / variables is =

**To call on the value of our first key in the object AFTER reassigning above**
```js
console.log(firstN)                    // prints Dillon
```
<br>

## Nested Destructuring

**This is an object that has one of its values set to another (nested) object**
```js
let obj = {                            // obj is the first object
    name: "Taylor" ,
    day:"Tuesday week2"
    schedule: {                        // schedule is the nested object
        morning: "lecture",
        lunch: "consume food",
        evening: "study while crying"
        }}
```
**Access the value associated with the ```lunch``` key**
```js
// destructure an object
let {schedule: {morning, lunch} } = obj

console.log(lunch)                     // consume food
```
The schedule IS NOT assigning anything, it is nesting into the next object with the extra pair of ```{ }```

**IF YOU DO NOT HAVE THE```{ }```YOU ARE REASSIGNING**

<br>

