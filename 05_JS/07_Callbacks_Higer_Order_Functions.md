## CallBacks & Higher Order Functions

### CallBacks
#### Named callbacks
- A function and some named callbacks

```js
let superAdd = function (num1, num2, cb) {
    // have a function
    let sum = num1 + num2;
    let res = cb(sum);
    // here, we are calling a named callback on line 21
    return res;
  }
  
  let doubler = function (n) {
    return 2 * n;
  }
  
  let negate = function (n) {
    return -1 * n;
  }
  
  console.log(superAdd(2,3,doubler));
  ```
  
---

### Anonymous callbacks
#### Same code, different callback structure
```js
let superAdd = function (num1, num2, cb) {
    let sum = num1 + num2;
    let res = cb(sum);
    // here, we are calling an anonymous callback res
    return res;
  }

let res = superAdd(3,2, function(n) {
    return 2 * n
  })

  console.log(res)
```
---

### Higher Order Functions
  #### A higher order function intakes another function as a parameter or returns another function as its value

  #### HOF Functionality 

  - Passing a CB as a parameter
  - Functions can be passed into other functions as callbacks because of HOF functionality

  - passing a callback function as a parameter:
```js
  let higherOrderFunction = function(callback){
    callback();
  };
  
  let intoAFunction = function() {
    console.log('I\'m being passed into a function');
  };
  
  let intoAFunctionPt2 = function() {
    console.log('I\'m ALSO being passed into a function');
  }
  
  higherOrderFunction(intoAFunction);
  higherOrderFunction(intoAFunctionPt2);
```



