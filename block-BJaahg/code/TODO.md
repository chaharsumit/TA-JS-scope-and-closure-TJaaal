## Understanding Scope and the difference between var, let and const

Watch this video before doing the exercise: https://www.youtube.com/watch?v=XgSjoHgy3Rk

1. Guess the output:

```js
let firstName = 'Arya';
const lastName = 'Stark';
var knownAs = 'no one';

console.log(
  window.firstName,
  window.lastName,
  window.knownAs
);

// undefined, undefined, 'no one'
```

2. Guess the output:

```js
let firstName = 'Arya';
const lastName = 'Stark';
var knownAs = 'no one';

function fullName(a, b) {
  return a + b;
}

console.log(window.fullName(firstName, lastName)); // "AryaStark"
```

3. Make a Execution Context Diagram for the following JS and write the output.

```js
fucntion addOne(num){
  return num + 1;
}
var one = addOne(0);
var two = addOne(1);
console.log(one, two); // 1 , 2
```

4. Make a Execution Context Diagram for the following JS and write the output.

```js
var one = addOne(0);
fucntion addOne(num){
  return num + 1;
}
var two = addOne(1);
console.log(one, two); // 1, 2
```

5. Make a Execution Context Diagram for the following JS and write the output.

```js
console.log(addOne(0)); // 1
function addOne(num){
  return num + 1;
}
var two = addOne(1);
console.log(two); // 2
```

6. Make a Execution Context Diagram for the following JS and write the output.

```js
var one = addOne(0); // Reference Error cannot use addOne before initialization
const addOne = (num) => {
  return num + 1;
};
var two = addOne(1);
console.log(two); // 2
```

7. Make a Execution Context Diagram for the following JS and write the output.

```js
console.log(addOne(0)); // Error addOne is not defined
const addOne = (num) => {
  return num + 1;
};
var two = addOne(1);
console.log(two); // 2
```

8. What will be the output of the following

```js
function isAwesome() {
  var awesome;
  if (false) {
    awesome = true;
  }
  console.log(awesome); // undefined 
}
isAwesome(); // undefined
```

9. What will be the output of the following

```js
function isAwesome() {
  let awesome;
  if (true) {
    awesome = true;
  }
  console.log(awesome); // true
}
isAwesome(); // true
```

10. What will be the output of the following

```js
function isAwesome() {
  let awesome;
  if (false) {
    awesome = true;
  }
  console.log(awesome); // undefined
}
isAwesome(); // undefined
```

11. What will be the output of the following

```js
let firstName = 'Arya';
const lastName = 'Stark';
var knownAs = 'no one';

function fullName(a, b) {
  return a + b;
}
const name = fullName(firstName, lastName);
console.log(name); // 'AryaStark'
```

12. Guess the output of the code below with a reason.

```js
function sayHello() {
  let name = 'Arya Stark';
}
sayHello();

console.log(name); // undefined
```

13. Guess the output of the code below with a reason.

```js
if (true) {
  var name = 'Arya Stark';
}
console.log(name); // 'Arya Stark'
```

14. Guess the output of the code below with a reason.

```js
if (true) {
  let name = 'Arya Stark';
}
console.log(name); // undefined
```

15. Guess the output of the code below with a reason.

```js
for (var i = 0; i < 20; i++) {
  //
}
console.log(i); // 20
```

16. Guess the output of the code below with a reason.

```js
for (let i = 0; i < 20; i++) {
  //
}
console.log(i); // Error i is not defined
```

17. Guess the output and the reason behind that.

```js
function sample() {
  if (true) {
    var username = 'John Snow';
  }
  console.log(username);
}
sample(); // 'John Snow'
```

18. Guess the output and the reason behind that.

```js
function sample() {
  if (true) {
    let username = 'John Snow';
  }
  console.log(username); // reference error username not defined
}
sample(); // 
```

19. Guess the output and the reason behind that.

```js
function sample() {
  var username = 'Arya Stark';
  if (true) {
    var username = 'John Snow';
    console.log(username); // 'John Snow'
  }
  console.log(username, 'second'); // 'John Snow' 'second'
}
sample();
```

20. Guess the output and the reason behind that.

```js
function sample() {
  let username = 'Arya Stark';
  if (true) {
    let username = 'John Snow';
    console.log(username, 'first'); // 'John Snow'
  }
  console.log(username, 'second'); // 'Arya Stark'
}
sample();
```

21. Guess the output and the reason behind that.

```js
function sample(...args) {
  for (let i = 0; i < args.length; i++) {
    let message = `Hello I am ${args[i]}`;
    console.log(message);
  }
}

sample('First', 'Second', 'Third'); 
 
'Hello I am First'
'Hello I am Second'
'Hello I am Third' 
```

22. Guess the output and the reason behind that.

```js
function sample(...args) {
  for (let i = 0; i < args.length; i++) {
    const message = `Hello I am ${args[i]}`;
    console.log(message);
  }
}

sample('First', 'Second', 'Third'); // 
'Hello I am First'
'Hello I am Second'
'Hello I am Third'
```

23. Guess the output and the reason behind that.

```js
if (true) {
  const myFunc = function () {
    console.log(username, 'Second');
  };
  console.log(username, 'First'); // Error cannot access 'username' before initialization
  let username = 'Hello World!';
  myFunc(); // 'Hello World!' 'Second' 
}
```

24. Guess the output and the reason behind that.

```js
function outer() {
  let movie = 'Mad Max: Fury Road';
  function inner() {
    console.log(
      `I love this movie called ${movie.toUpperCase()}`
    );
  }
  inner();
}

outer(); // 'I love this movie called MAD MAX: FURY ROAD'
```

25. Guess the output and the reason behind that.

```js
function outer() {
  let movie = 'Mad Max: Fury Road';
  function inner() {
    let movie = 'Before Sunrise';
    console.log(
      `I love this movie called ${movie.toUpperCase()}` // 'I love this movie called BEFORE SUNRISE'
    );
  }
  inner();
}

outer();
```

26. Guess the output and the reason behind that.

```js
function outer() {
  let movie = 'Mad Max: Fury Road';
  function inner() {
    let movie = 'Before Sunrise';
    function extraInner() {
      let movie = 'Gone Girl';
      console.log(
        `I love this movie called ${movie.toUpperCase()}` // 'I love this movie called GONE GIRL'
      );
    }
    extraInner();
  }
  inner();
}
outer();
```

30. Using reduce find the final value when the initial value passed is `100`. You have to pass the output of one function into the input of next function in the array `allFunctions` starts with `addOne` ends with `half`.

```js
const addOne = (num) => {
  return num + 1;
};
const subTwo = (num) => {
  return num - 2;
};
const multiplyThree = (num) => {
  return num * 3;
};
const half = (num) => {
  return num / 2;
};

let allFunctions = [
  addOne,
  subTwo,
  multiplyThree,
  addOne,
  multiplyThree,
  half,
];

// Answer is: 447
```
