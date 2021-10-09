## Getting to understand closure properly

1. Write a function called `multiplyBy` that takes a `number` as an argument and returns a function. Returned function takes another `number` as an argument and returns the multiplication of both the numbers.

```js
function multiplyBy(num){
  return function cb(num2){
    return num * num2;
  };
}

const double = multiplyBy(2);
const final = double(15); // final should be 30
```

2. Write a function called `fullName` that takes a string `firstName` as an argument and returns a function. Returned function takes another string `lastName` as an argument and returns full name.

```js
function fullName(firstName){
  return function fName(str){
    return `${firstName} ${str}`;
  };
}
const name = fullName('Will');
const final = name('Smith'); // final should be "Will Smith"
```

3. Write a function called `isInBetween` which takes two parameter `a` and `b` and returns a function. When you call the returned function with any number it returns `true` if the value is in between `a` and `b`.

```js
function isInBetween(a, b) {
  return function compare(num){
    if(num < b && num > a){
      return true;
    }
    return false;
  };
}
const isChild = isInBetween(10, 100);
isChild(21); // true
isChild(45); // true
isChild(103); // false
```

4. Write a function call `letsWishThem` that take one parameter `string` called `greeting` and returns a function that takes another argument called `message`.

```js
function letsWishThem(greeting) {
  return function getMessage(message){
    return `${greeting} ${message}`;
  };
}
const callWithHey = letsWishThem('Hey');
const callWithHello = letsWishThem('Hello');
callWithHey('Arya'); // Hey Arya
callWithHello('How Are You?'); // Hello How Are You?
```

5. Write a function called `addGame` which takes a string (name of the game) and the current score. It returns a function calling that will increment the score by one and print something like `Score of Basketball is 1`.

```js
function addGame(gameName, currScore) {
  return function newScore(){
    ++currScore;
    return `Your score of ${gameName} is ${currScore}`;
  }
}
// Output
const hockey = addGame('Hockey', 0);
hockey(); // Your score of Hockey is 1
hockey(); // Your score of Hockey is 2
const cricket = addGame('Cricket', 1);
cricket(); // Your score of Cricket is 2
cricket(); // Your score of Cricket is 2
```

6. Write a function called `getCard` which takes one of these options (club, spade, heart, diamond) returns a function calling that function returns random card (2,3,4,5,6,7,8,9,10,J, Q, K, A) of that suit.

```js
function getCard(suit) {
  let arr = ['2','3','4','5','6','7','8','9','10','J','Q','K','A'];
  const randomElement = arr[Math.floor(Math.random() * arr.length)];
  return function randomCard(){
    return `Card is: ${randomElement} ${suit}`;
  };
}
const randomClub = getCard('Club');
randomClub(); // Card is: 6 Club
randomClub(); // Card is: A Club
const randomSpade = getCard('Spade');
randomSpade(); // Card is: 6 Spade
randomSpade(); // Card is: A Spade
```
