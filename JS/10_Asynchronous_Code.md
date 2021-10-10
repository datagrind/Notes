## Asynchronous Coding 

### Threading 
- Threading is how programming languages line up tasks to execute 

- Javascript is a single-threaded language

#### Thread of execution
    - A sequence of tasks / commands

- Single-threaded execution
    - Only ONE task can be processed at a time
    - Processing happens top-down

- Multi-threaded execution
    - Multiple tasks can be process at a time
    - Threads must wait for resources for execution -- not always faster

```js
// Example 1:
    function nextTask() {
        console.log('done');
    }

    setTimeout(function () {
        console.log('times up!');
    }, 1000);

    nextTask();        
    
```

```js
// $ example 2:
    function blockingTheThread() {
        while (true) {}
    }

    setTimeout(function () {
        console.log('times up!');
    }, 1000);

    blockingTheThread();        
    
```

---

### Event Queue:
- Event Loop
    - The model of execution

    - Two parts in JS:
        - Call Stack
            - Tracks the 'current task in progress'
        - Message Queue
            - Tracks the 'to-do' tasks.


---

### Sync vs Async:

#### Synchronous Code
- Doing one task at a time
      
#### Asynchronous Code
- Leaving a process to finish and run more code while you're waiting.

- Using setTimeout:
    - when a setTimeout function executes after its "num" ms waiting period it PUSHES ITS EXECUTION ONTO THE CALL STACK
        - it DOES NOT EXECUTE -- it gets *put into the queue* to execute

```js
// $ example 1:
    let foo = function () {
        console.log('two');
    };

    console.log('one');

    setTimeout(foo, 500)

    console.log('three');
        
        // Prints: 
        //        one               // ? 
        //        three             // ? 
        //        two
```    

```js
// $ example 2: 
    function somethingSlow() {
        // some terribly slow implementation
        // assume that this function takes 4000 milliseconds to return
    }
    
    function foo() {
        console.log("food");
    }
    
    function bar() {
        console.log("bark");
        baz();
    }
    
    function baz() {
        console.log("bazaar");
    }
    
    setTimeout(foo, 1500);
    setTimeout(bar, 1000);
    somethingSlow();
```

---

### setTimeout
 ```js
let counter = 0;
let timeoutObj = setInterval(function () {
    counter += 1
    console.log(counter);
    if (counter === 10) {
        console.log("logged out");
        clearInterval(timeoutObj);
    }
}, 1000)

setTimeout(() => (counter = 0), 5000)
```