
## String Interpolation
#### Ever seen ```${ }``` in javascript? 

```js
let firstName = 'Doctor'
let lastName = 'Who'

// ! anything inside `${ } ` will be interpreted as javascript
let sentence = `hello ${firstName} ${lastName}`
      // hello Doctor Who

// | Basic expressions work as well
let sentence2 = `${2+1} is larger than ${2-1}`
      // 3 is larger than 1
```


