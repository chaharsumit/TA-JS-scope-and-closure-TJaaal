1. Convert the function below into different forms of function expression.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}

// Your code goes here

let  percentage = function percentage(marks, total){
  return (marks * 100) / total;
};

let percentage = function (marks,total){
  return (marks * 100) / total;
}

let percentage = (marks, total) => {
  return (marks * 100) / total;
}
```

2. Write Function Declaration or Function Expression next to the function.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}
// declaration
```

```js
let percentage = function percentage(marks, total) {
  return (marks * 100) / total;
};
// expression
```

```js
let percentage = function (marks, total) {
  return (marks * 100) / total;
};
// expression
```

```js
let percentage = (marks, total) => {
  return (marks * 100) / total;
};
// expression
```

```js
let percentage = (marks, total) => (marks * 100) / total;
//expression
```

3. Why is a function definition an expression in JavaScript? Give one example of function expression.

// function definition is an expression because it is used to execute the set of statements given when function is invoked.for example, let add = (a,b) => {return a+b;};

4. Why is a function call an expression in JavaScript?

// function call is also an expression as its outcome is the result of execution of statements in the called function's definition. 

5. Write VALID and INVALID next to each example below with the reason.

```js
function add(a, b) {
  return a + b;
}

let five = add(2, 3); // valid returns -> 5 add function is executed it returns five and then its return value is assigned to the variable five.
five = add; // valid five has reference to the add function
five = five(10, 11); // valid 21 five is now having same statements as in add so it return the added value of both the parameters
five = function () {
  return 'Hello';
}; // 'Hello' is returned as five is now assigned a new reference to its anonymous function in the above expression
```

6. What is the difference between function definition and function call? Explain with an example.

// the difference between a function definition and function call is that the function definition includes the set of statements or steps that are to be performed whenever we invoke the function. Whereas, a function call is when we actually invoke the function to get a result out of it, which includes the execution of various statements and expressions inside the function declaration.
for example,
(1)
function add(x, y){
	let sum = x + y;
	return sum;
}

(2)
add(2,3);

Above, in (1) we have our function declaration which includes the set of steps to be performed in the execution of this function. Whereas, in (2) we are calling the function add to get the return vlue of sum out of the function by performing the steps on our given parameters.

7. What is the similarities between function definition and function call?

// the similarities between a function definition and a function call is that both of them require the name of the function or its reference for anonymous functions and the parenthesis to declare the function as well as to call them passing the parameters in parenthesis if there exists any in the function declaration

8. Is the code below valid or invalid. Explain with reason.

```js
function hello() {
  console.log('Hello World!');
}

hello.user = 'Sam'; // valid as function is also an object and we can give it a key-value pair.
```

9. What is higher order function explain with an example.

// a higher order function is javaScript is a type of function that receives or returns a function as arguments.

10. Explain what is callback function. Why you can pass a function inside a function?

// A callback function is  a function that is called from another function to perform some task and return a value to the calling function. for example, if we want to add two numbers and then divide them by 2 we can do it like this with callback functions,

function divideNsum(x, y){
	let sum = add(x,y);
	return sum / 2;
}

function add(x,y){
	return x + y;
}

here we use add as our callback function for returning the sum of two values and then our calling function returns the result by diving them sum by 2;
