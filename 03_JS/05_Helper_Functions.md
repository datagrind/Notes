# Helper Functions
 **Helper Functions are functions written outside the main code block that help to keep code readable and modular**

***Write a function that takes in an array of numbers and returns a new array that contains only the even numbers***
```js
// Helper Function:
function isEven(num){                       // function isEven with parameter num
    return num % 2 === 0;                   // returns true if the number is even
};

// Main Code Block:
function extractEvens(numbers){             // function extractEvens with parameter numbers
    let evens = [];                         // new empty array evens
    for(i = 0; i < numbers.length; i++){    // iterate through array argument
        if (isEven(numbers[i])){            // call helper function inside main code block
            evens.push(num);                // add even numbers to evens array
        }
    }
    return evens;                           // return evens array
};

console.log(extractEvens([3,5,4,7,8]));     // [4,8]
```
<br>

```js
//Helper Function:
   let isPrime = function(num){
    if (num < 2) {
        return false
    }

    for (let i = 2; i < num; i++){
        if (num % i === 0) {
            return false
        }
    }
    return true
};

// Main Code Block:
let pickPrimes = function(nums) {
    let primes = []

    for (let i = 0; i < nums.length; i++){
        let num = nums[i]
        if (isPrime(num)){
            primes.push(num)
        }
    }
    return primes
};
```
<br>

***Write a function that intakes a string and removes all words that are less than 5 letters***
```js
// Helper Function:
let isLessThanFive(word){
    let lengthOfWord = word.length
    return lengthOfWord < 5                   // ? Return words that are less than five
};

// Main Code Block:
let removeSmallWords = function(str){
    let results = [];
    let split = str.split(' ');               // ? splits the string on spaces
    for(i = 0; i < split.lenghth; i++){
        let word = split[i];
        if (!isLessThanFive(word)){           // ? if the number is not less than five
            results.push(word);
        }
    }
    return results.join(' ');
}

console.log(removeSmallWords('the cat is awesome'));
console.log(removeSmallWords('hello world'));
console.log(removeSmallWords(''));
```
