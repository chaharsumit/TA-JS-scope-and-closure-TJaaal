## Closure Exercise

1. Write a function, `outer` that takes an input `string`. Inside the function `outer` define another function expression named `sayHello` which alerts the `input`. `sayHello` should be call immediately after it is defined.

```js
function outer(str){
  function sayHello(){
    console.log(str);
  };
  sayHello();
}
```

2. Write a function `delay` that accepts two arguments, a callback and the wait for the time in milliseconds (1000 ms is 1 second). `delay` should return a function that, when invoked waits for the specified amount of time before executing. (Use setTimeout)

```js
function delay(cb, time){
  return function(){
    setTimeout(cb(), time);
  }
}
```

3. Write a function with a closure. The first function should only take one argument, someone's last name, and return the inner function. The returned `inner` function should take one more argument, someone's first name. When inner function when called it should console.log both the first name and the last name with a space.

```js
function lastName(last) {
  return function inner(first){
    console.log(`${first} ${last}`);
  }
}
let lastNameLee = lastName('lee'); // logs nothing
lastNameLee('Brett'); //logs 'Brett Lee'
```

This function is useful in case you want to create name for multiple people with same last name.

```js
lastNameLee('Jane'); //logs 'Jane Lee'
lastNameLee('Lynne'); //logs 'Lynne Lee'
```

4. Create a `storyWriter` function that returns an object with two methods. One method, `addWords` adds a word to your story and returns the story while the other one, `erase`, resets the story back to an empty string. Here is an implementation:

```js
function storyWriter() {
  let story = '';
  let myObj = {
    addWords: function(word){
      return story += word;
    },
    erase: function(){
      return story = '';
    }
  };
  return myObj;
}

// Test
let farmLoveStory = storyWriter();
farmLoveStory.addWords('There was once a lonely cow.'); // 'There was once a lonely cow.'
farmLoveStory.addWords('It saw a friendly face.'); //'There was once a lonely cow. It saw a friendly face.'
farmLoveStory.erase(); //''

let storyOfMyLife = storyWriter();
storyOfMyLife.addWords('My code broke.'); // 'My code broke.'
storyOfMyLife.addWords('I ate some ice cream.'); //'My code broke. I ate some ice cream.'
storyOfMyLife.erase(); // ''
```

5. Create a function named `forEach` which accepts one parameter an array. Inside the function `forEach` there a variable named `index` which is initialized to `0`.

When `forEach` function is called it returns another function. When the returned function is called it returns the element from the array at specific index. Every time you call the returned function the value of index should increment.

```js
function forEach(arr) {
  let index = 0;
  return function(){
    return arr[index++];
  }
}

let next = [1, 2, 3, 4, 5];
next(); // 1
next(); // 2
next(); // 3
next(); // 4
next(); // 5
```

6. Create a function named `addDesignation` which accepts a `title` and returns another function.

The returned function accepts a string `prefix` and returns `prefix` and `title` with a space.

```js
function addDesignation(title) {
  return function(prefix){
    return `${prefix} ${title}`;
  }
}

let sales = addDesignation('Salesman');
sales('Main'); // Main Salesman

let manager = addDesignation('Manager');
manager('Regional'); // Regional Manager
manager('Head'); // Head Manager
```

7. Create a function named `changeSalary` which accepts `currentSalary` (number) and returns an object that contains three methods

- `raise` which will add `500` to the current salary and returns the updated salary
- `lower` will decrease the salary by 500 returns the updated salary
- `current` will return the current salary returns the updated salary

```js
function changeSalary(currSalary) {
  let myObj = {
    raise: function(){
      return (currSalary + 500);
    },
    lower: function(){
      return (currSalary - 500);
    },
    current: function(){
      return (currSalary);
    }
  }
  return myObj;
}

let sam = changeSalary(2000);
sam.raise(); // 2500

let arya = changeSalary(4000);
arya.lower(); // 3500
```

8. Create a function named `nameFactory` which accepts `firstName` and `lastName` and returns an object with multiple functions.

- `getFullName`: return the full name of the person with a space
- `setFirstName`: accepts a parameter first name using which updates the firstName and return the updated full name
- `setLastName`: accepts a parameter last name using which updates the firstName and return the updated full name

```js
function nameFactory(firstName, lastName){
  let myObj = {
    getFullName: function(){
      return `${firstName} ${lastName}`;
    },
    setFirstName: function(name){
      firstName = name;
      return `${firstName} ${lastName}`;
    },
    setLastName: function(last){
      lastName = last;
      return `${firstName} ${lastName}`;
    }
  };
  return myObj;
}

let arya = nameFactory('Arya', 'Stark');
arya.getFullName(); // "Arya Stark"
arya.setFirstName('Jon'); // "Jon Stark"
arya.setLastName('Lannister'); // "Jon Lannister"
```

9. Create a function named `createTag` which accepts an HTML element name and returns another function.

The returned function accepts a string (children) and returns the children with the tag you passed.

```js
function createTag(name){
  return function(children){
    return `<${name}>${children}</${name}>`;
  };
}

let bold = createTag('b');
bold('Hello World!'); // <b>Hello World!</b>

let italic = createTag('i');
italic('Hello World!'); // <i>Hello World!</i>
```
