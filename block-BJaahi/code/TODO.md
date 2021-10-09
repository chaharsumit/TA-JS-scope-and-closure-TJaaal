For the given code below:

- re-write the code in ways that system will understand

For Example:

1.

```js
var username = 'Arya';
let brothers = ['John', 'Ryan', 'Bran'];

console.log(username, brothers[0]);

function sayHello(name) {
  return `Hello ${name}`;
}

let message = sayHello(username);
var nextMessage = sayHello('Test');
```

<!-- Answer -->

```js
// Declaration Phase
var username = undefined;
let brothers;

function sayHello(name) {
  return `Hello ${name}`;
}

let message;
var nextMessage = undefined;

// Execution Phase

username = 'Arya';
brothers = ['John', 'Ryan', 'Bran'];

console.log(username, brothers[0]);

message = sayHello(username);
nextMessage = sayHello('Test');
```

2.

```js
console.log(username, numbers);

var username = 'Arya';
let number = 21;

function sayHello(name) {
  return `Hello ${name}`;
}

let message = sayHello(username);
var nextMessage = sayHello('Test');
```

<!-- Answer -->

```js
//Declaration phase
var username = undefined;
let number;
function sayHello(name){
	return `Hello ${name}`;
}
let message;
var nextMessage = undefined;

//Execution phase
username = 'Arya';
number = 21;
message = sayHello(username);
nextMessage = sayHello('Test');
```

3.

```js
console.log(username, numbers);
let username = 'Arya';
let number = 21;

let sayHello = function (name) {
  return `Hello ${name}`;
};

let message = sayHello(username);
var nextMessage = sayHello('Test');
```

<!-- Answer -->

```js
// declaration phase
let username;
let number;
let sayHello;
let message;
var nextMessage = undefined;

//execution phase
username = 'Arya';
number = 21;
sayHello = fn;
message = sayHello(username);
nextMessage = sayHello('Test');
```

4.

```js
let username = 'Arya';
console.log(username, numbers); // Error

let number = 21;
let message = sayHello(username); // Error

let sayHello = function (name) {
  return `Hello ${name}`;
};

var nextMessage = sayHello('Test');
```

<!-- Answer -->

```js
// declaration phase
let username;
let number;
let message;
let sayHello;
var nextMessage = undefined;

// execution phase
username = 'Arya';
console.log(username,number); // Error
number = 21;
message = sayHello(username); // Error
sayHello = fn;
nextMessage = sayHello('Test');
```

5.

```js
console.log(name);
console.log(age);
var name = 'Lydia';
let age = 21;
```

<!-- Answer -->

```js
// declaration phase
var name = undefined;
let age;
// execution phase
console.log(name); // undefined
console.log(age); // Error age is not defined
name = 'Lydia';
age = 21;
```

6.

```js
function sayHi(name) {
  console.log(name);
  console.log(age);
  var name = 'Lydia';
  let age = 21;
}

sayHi();
```

<!-- Answer -->

```js
// declaration phase
function sayHi(name){
	console.log(name);
	console.log(age);
	var name = undefined;
	let age;
}
// execution phase
sayhi(name){
	console.log(name); // undefined
	console.log(age); // cannot use age before initialization
	name = 'Lydia';
	age = 21;
}
```

7.

```js
sayHi();
function sayHi(name) {
  console.log(name);
  console.log(age);
  var name = 'Lydia';
  let age = 21;
}
```

<!-- Answer -->

```js
// declaration phase
function sayHi(name){
	console.log(name);
	console.log(age);
	var name = undefined;
	let age;
}
// execution phase
sayhi(name){
	console.log(name); // undefined
	console.log(age); // cannot use age before initialization
	name = 'Lydia';
	age = 21;
}
```

8.

```js
sayHi();
let sayHi = function sayHi(name) {
  console.log(name);
  console.log(age);
  var name = 'Lydia';
  let age = 21;
};
```

<!-- Answer -->

```js
// declaration phase
let sayHi;

// execution phase
sayHi = function sayHi(name){
	console.log(name);
	console.log(age);
	var name = 'Lydia';
	let age = 21;
}
// Error comes as sayHi is not defined when we call it as it is declared with a let keyword
```

9.

```js
let num1 = 21;
console.log(sum);
var sum = num1 + num2;
let num2 = 30;
```

<!-- Answer -->

```js
// declaration phase
let num1;
var sum = undefined;
let num2;

// execution phase
num1 = 21;
console.log(sum); // undefined
sum = 21 + undefined; // NaN
num2 = 30;
```

10.

```js
var num1 = 21;

let sum2 = addAgain(num1, num2, 4, 5, 6);

let add = (a, b, c, d, e) => {
  return a + b + c + d + e;
};
function addAgian(a, b) {
  return a + b;
}
let num2 = 200;

let sum = add(num1, num2, 4, 5, 6);
```

<!-- Answer -->

```js
// declaration phase
var num1 = undefined;
let sum2;
let add;
function addAgain(a,b){
	return a + b;
}
let num2;
let sum;

// execution phase
num1 = 21;
sum2 = //Error cannot access num2 before initialization
add = (a, b, c, d, e) => {
  return a + b + c + d + e;
};
num2 = 200;
sum = add(21,200,4,5,6); // 236
```

11.

```js
function test(a) {
  let num1 = 21;
  return add(a, num1);
}

let sum = test(100);

let add = (a, b) => {
  return a + b;
};
```

<!-- Answer -->

```js
// declaration phase
function test(a) {
  let num1 = 21;
  return add(a, num1);
}
let sum;
let add;

// execution phase
sum = test(100); // Error add is not defined
add = (a, b) => {
  return a + b;
};
```

12.

```js
function test(a) {
  let num1 = 21;
  return add(a, num1);
}

let sum = test(100);

function add(a, b) {
  return a + b;
}
```

<!-- Answer -->

```js
// declaration phase
function test(a) {
  let num1 = 21;
  return add(a, num1);
}
let sum;
function add(a, b){
	return a + b;
}

// execution phase
sum = test(100); // 121
```
