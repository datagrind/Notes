## Scope and Hoisting

### Scope 
- The scope of a program in JS is the set of variables that are accessible at a given location in that program

#### Types of Scope in JS
- Global
    - Variables defined in the global scope.
- Local or Function
    - Global, Parameters, Variables in the function
- Block 
    - Global, Local, Variables in the block

#### Global Scope:
```js
    const bear = {sound: "RAWR!" }
```
#### Local (Function) Scope:
- Variables declared inside of a function are 'locally-scoped'
- They cannot be referenced outside of the function
```js
    function bearMaker(name){
        return "I'm " + name + " the bear Rawr!"
    }
    console.log(bearMaker("Miley"));
```
- Here, the bearMaker function has access to:
    - incoming arguments (name)
    - variables declared in the function (bearString)
    - Function Scope also has access to previously declared variables in the Global Scope

#### Block Scope:
```js
    if (true) {
        let candle = "fire!"
        console.log(fire);
    }
```
---

#### Here's that Local Scope again:
```js
    function bearMaker(name){
        return "I'm " + name + " the bear Rawr!"
    }
    console.log(bearMaker("Miley"));
```
- Here, the bearMaker function has access to:
    - incoming arguments (name)
    - variables declared in the function (bearString)
    - Function Scope also has access to previously declared variables in the Global Scope

#### Scope Chaining:
- When a function is given a variable it does not have declared in its scope 
- it will attempt to find a variable within the scope
- and then go up one scope level to find the variable

Example 1:
```js
    function garden() {
        let flower = "lily"

        function flowerBed(){
            console.log(flower)
        }
        flowerBed();
    }
    garden();                            // "lily"
```
Example 2:
- A function will always use the scope closest to it first
- Variable scope works inside ---> to out, but not outside to in
```js
    function garden() {
        let flower = "lily"

        function flowerBed(){
            let flower = "Not a lily"    // closest scope for flowerBed
            console.log(flower)
        }
        flowerBed();
    }
    garden();                            // "Not a lily"
```

---

### Variable Types
#### Const, Let, and Var

#### let
Functions with let
```js
let hungry = false

    function sayHungry() {
        let hungry 
        hungry = true

        if (hungry) {
            let hungry = potato
            console.log(hungry);        // potato
        }
        console.log(hungry);            // true
    }
    console.log(hungry);                // false
```

### var
#### Functions with var
- (Don't Use Var)
- Var is block-scoped and has... weird... behavior 
```js
var hungry = false

    function sayHungry() {
        var hungry 
        hungry = true

        if (hungry) {
            var hungry = potato
            console.log(hungry);        // potato
        }
        console.log(hungry);            // potato
    }
    console.log(hungry);                // false
```

### const 
#### Functions with const
- const CANNOT be redefined -- it stands for 'constant'
- const is block-scoped
- const CAN be reinitialized (a variable of the same name can be initialized) by using const again in a different block
```js
const hungry = false

    function sayHungry() {
        const hungry 
        hungry = true

        if (hungry) {
            const hungry = potato
            console.log(hungry);        // potato
        }
        console.log(hungry);            // true
    }
    console.log(hungry);                // false
```
---

### Hoisting
#### var
```js
    function hoist(){
        console.log(dog)
        var dog = 'Rosie'
        // var is "hoisted" -- variable dog can be called before it is declared
    }

    hoist();
```

- var is weird, don't use it
```js 
    return var
    var food = "egg"
    // here return var will return undefined 

    var food;
    return var;
    food = "egg"    
    // here due to hoisting var food can be initialized after being called
    // and it will still work because it was already declared 
```
#### let 
```js
    function hoist(){
        console.log(dog)
        let dog = 'Rosie'                  
        // temporal dead zone -- variable dog cannot be used before declaring
    }

    hoist();
```

#### const
```js
function hoist(){
    console.log(dog)
    const dog = 'Rosie'                  
    // temporal dead zone -- variable dog cannot be used before declaring
}

hoist();
```
---

### Closures
#### Closures are HUGE in job interviews
- An inner function that uses (or changes) variables that were initialized in an outer function

```js
    // Example 1:
    function appleTree() {
        let aVariable = 'apple';

        function tree() {
            // the inner function has access to the outer function
            return aVariable;               
            // returns a `closed over` variable `aVariable`
        }

        return tree();
    }
    console.log(appleTree());             // "apple"
```
---
```js
    // Example 2:
    function appleTree2() {
        let tree = { type: 'apple', grown: false };
    
        function growTree() {
            tree.grown = true; 
            // changing a `closed over` variable `tree`
        }
    
        growTree();
        return tree;
    }
    console.log(appleTree2());
```
---
```js
    // Example 3:
    function treeMaker() {
        let trees = [];
    
        function addTree(tree) {
            trees.push(tree);
            return trees;
        }
    
        return addTree; 
        // remember, we are returning a function here
    }
    
    const treeFunc = treeMaker();
    console.log(treeFunc);
    console.log(treeFunc('Pine'));
```
---
```js
    // Example 4:
    function createCounter() {
        let count = 0;
    
        return function () {
            // we are returning an anonymous function here
            count++; 
            // we are changing a closed over variable here
            return count;
        };
    }
    let counter1 = createCounter();
    console.log(counter1);
    console.log(counter1());
    console.log(counter1());
    
    let counter2 = createCounter();
    console.log(counter2);
    console.log(counter2());
    console.log(counter2());
```
---
```js
    // Example 5: 
    function pizzaMaker(food) {
        // we are inside the `outer` function
        let order = "I'd like a pizza with ";
    
        function oven() {
            // we are inside the `inner` function
            return order + food; 
            // food comes from the outer scope (see line 265)
        }
    
        return oven();
    }
    
    console.log(pizzaMaker('cheese'));
```
---
```js
    // Example 6:
    function groceryList(list) {
        let groceries = list;                      // [ 'milk, 'eggs' ]
    
        function addItem() {
            groceries.push('and ice cream!');      // [ 'milk', 'eggs', 'and ice cream' ]
            // mutates closed over `groceries` variable
        }
    
        addItem();
        return groceries;                          // [ 'milk', 'eggs', 'and ice cream' ] 
    }
    console.log(groceryList(['milk', 'eggs']));
```
---
```js
   // Example 7:
   function elephantCollector() {
    const elephants = ['dumbo'];

    return function (name) {
        // we are returning a FUNCTION
        elephants.push(name);
        return elephants; 
        // this is a CLOSED OVER variable
    };
    }

    const elephantParade = elephantCollector();
        // returns a function
    console.log(elephantParade);
    console.log(elephantParade('Obi'));
    console.log(elephantParade('Gerald'));
```
---
