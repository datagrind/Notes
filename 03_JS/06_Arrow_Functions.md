### Arrow Functions
#### A way to implicitly return without an explicit return statement
```js
    let firstArrow = (num) => num + 1;

    console.log(firstArrow(1));             // 2
```
---
```js
    let arr = [1,2,3];

    let arrPlusOne = (arr) => arr.map((el) => el + 1);

    console.log(arrPlusOne(arr)); // [2, 3, 4]
```