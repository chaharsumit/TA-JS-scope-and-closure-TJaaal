1. Create a function by your choice that accepts a callback function.

function multiplyAndDivide(a = 0, b = 0, cb1, cb2){
  let result = cb2(cb1(a,b));
  return result;
}

function multiply(a,b){
  return a * b;
}

function divide(num){
  return num / 2;
}

multiplyAndDivide(10,20,multiply, divide);

2. Create a function by you choice that returns a function reference.

function returnReference(cb){
  return cb2;
}

function multiply(a,b){
  return a * b;
}

returnReference(multiply);

3. Create a higher order function called `map` that takes two inputs:
   - An array of numbers/string/boolean etc
   - A 'callback' function - a function that is applied to each element of the array (inside of the function 'map')

Have `map` return a new array filled with values that are the result of the 'callback' function on each element of the input array.

```js
// Your code goes here

// Test Your Code
function map(arr, cb){
  let finalArr = [];
  for(elem of arr){
    finalArr.push(cb(elem));
  }
  return finalArr;
}

function multiplyByTwo(n) {
  return n * 2;
}
map([1, 2, 3, 4, 5], multiplyByTwo); //-> [2,4,6,8,10]
multiplyByTwo(1); //-> 2
multiplyByTwo(2); //-> 4
```

4. Create a higher-order function called `forEach` taht takes an array and a callback, and runs the callback on each element of the array. `forEach` does not return anything.

```js
// Your code goes here

// Test Your Code
function forEach(arr, cb){
  for(char of arr){
    cb(char);
  }
}
let alphabet = '';
let letters = ['a', 'b', 'c', 'd'];
forEach(letters, function (char) {
  alphabet += char;
});
console.log(alphabet); //prints 'abcd'
```

5. Create higher-order function called `filter` takes an array and a callback, and runs the callback on each element of the array if the return value of callback is `truthy` store in new array return the new array.

```js
// Test Your Code
function filter(arr, cb){
  let finalArr = [];
  for(elem of arr){
    if(cb(elem)){
      finalArr.push(elem);
    }
  }
  return finalArr;
}
var numbers = [1, 3, 5, 4, 7, 89, 234, 20];
let even = filter(numbers, function (n) {
  return n % 2 === 0;
});
console.log(even); // [4,234,20]
let odd = filter(numbers, function (n) {
  return n % 2 !== 0;
});
console.log(odd); // [1,3,5,7,89]
```
