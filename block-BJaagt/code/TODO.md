Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

Example:

```js
function hello() {
  var username = 'Arya';
}
console.log(useranme); // output
```

In above code we are looking for the variable named `username`. There is no variable named `username` in the global scope. The variable is inside the function named `hello` and we can't access the variable defined inside a function from outside.

The above code will throw an error `Reference Error username is not defined`.

2. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
{
  const username = 'Arya';
}
console.log(useranme); // error
```

In the code the const variable named 'username' is defined inside a block of code so it is local to that particular block of code and is not visible outside of it.
The Reference Error is thrown 'username is not defined'.

3. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  let username = 'Arya';
}
console.log(useranme); // error
```
In the code the 'let' type of variable named 'username' is defined inside a block of code i.e, the if statement's scope so it is local to that particular block of code and is not visible outside of it.
The Reference error of username is not defined is thrown

4. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  var username = 'Arya';
}
console.log(useranme); // Arya
```

In this code the username 'Arya' will be printed as the declaration is done using the var keyword so its is only function scoped so we can access a variable from outside if its declared inside a block scope so.




5. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
if (true) {
  var username = 'Arya';
}
console.log(useranme); // error
```

In this code we have declared the variable username twice on in global scope and second in the if statement's block thus as we know if we declare something using let or const then we can't declare that variable again in our code.

It will throw an error saying the identifier 'username' has already been declared



6. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
if (true) {
  let username = 'Arya';
}
console.log(useranme); // output
```

Here in the above code the username is again declared twice but in this case the two variables are actually different as one is in the global scope an the other is in the block scope of 'if statement' thus the code is perfectly valid.

the output for this is 'John' as we are referencing the value of global username variable in our console.log statement thus it will print 'John'.

7. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
function sayHello() {
  let username = 'Arya';
}
sayHello();
console.log(username); // output
```

Here again the declarations for the same variable happen twice and both the two variables are actually different thus if we modify one then the other's state won't be altered.

The output will be 'John' as when we call sayHello() it just makes its own variable username to have the value of "Arya" but as the global username is a completely different entity, thus the state of it is not altered so the result comes to be "John".


8. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (var i = 0; i < 10; i++) {
  console.log(i, 'First'); // 0,1,2,3,4,5,6,7,8,9,10
}
console.log(i, 'Second'); // 10
```

In the above code we declare the variable 'i' in the list of conditions for out for loop but 'var' is actually only function scoped so it will be visible outside the block scope that is for loop's scope so the code is perfectly valid here.

The output for the second statement here will be `10 "Second"` as 'var' is only function scoped and 'i' is as a result visible globally in our code so the final value of 'i' after the loop ends is '10' which is the value printed.


9. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (let i = 0; i < 10; i++) {
  console.log(i, 'First'); // 0,1,2,3,4,5,6,7,8,9,10
}
console.log(i, 'Second'); // ReferenceError
```

Here we go same as the earlier code but the difference is we use 'let' here instead of 'var' so let is both function and block scope so its only visible inside the scope where it is declared. Thus the code becomes invalid when we come to our console.log in the global scope.

The ReferenceError is thrown for the global console.log statement but it works fine for the console.log statement inside the for loop.

