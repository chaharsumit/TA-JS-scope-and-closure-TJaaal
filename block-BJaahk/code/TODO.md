## Closure Examples

1. Create a function named `censor` which accepts two parameter (fromWord, toWord) and returns a function when called.

The returned function accepts a sentence. If the sentence contains the `fromWord` it should be replaced with `toWord`. Finally when the returned function is called it should return the new sentence.

```js
function censor(fromWord, toWord) {
  return function getSentence(sentence){
    if(sentence.includes(fromWord)){
      return sentence = sentence.replace(fromWord, toWord);
    }
  };
}

let censorSentence = censor('World', 'Sam');
censorSentence('Hello World'); // Hello Sam

let censorQuote = censor('die', 'live');
censorQuote(`all men must die`); // all men must live
```

2. Create a function named `multipleCensor` which does not accept any parameter and returns a function.

The returned function either accepts two parameter or one parameter.

- When you pass two parameter it adds the words to an array something like `'World', 'Sam'` and does not return anything.
- When you pass one parameter it should return a string with words replaced with the required words.

```js
function multipleCensor() {
	let arr = [];
  return function(...params){
  	if(params.length === 1){
  		let quote = params[0];
  		words.forEach(pair => {
  			quote = quote.replace(pair[0], pair[1]);
  		});
  		return quote;
  	}else if(params.length === 2){
  		words.push(params);
  	}else{
  		alert('invalid numbers of parameters');
  	}
  }
}

let censorQuote = multipleCensor();
censorQuote('forget', 'remember'); // two parameter no return
censorQuote('never', 'always'); // two parameter no return
censorQuote('hurt you', 'love you'); // two parameter no return

censorQuote(
  'Never forget what you are. The rest of the world will not. Wear it like armor, and it can never be used to hurt you.'
);

// Returns: "Never remember what you are. The rest of the world will not. Wear it like armor, and it can always be used to love you."
```

3. Create a function named `createCache` which accepts two parameters - a callback function and a string. The string will act like a password. When the function (`createCache`) is called it should return another function. Take a look at the example to understand it better.

The returned function accepts one parameter.

- If the parameter is anything other than the password, that value will be passed to the callback function. The returned value from the callback function will be stored inside an object. The key will be the parameter and the value will be the output of the callback function. It will also return the returned value from the callback function.

- If the parameter is the same as the password it will return the object in which we stored the values.

```js
function createCache(cb, pwd) {
  let obj = {};
  return function(param){
  	if(param !== pwd){
  		obj[param] = cb(param);
  		return cb(param);	
  	}else{
  		return obj;
  	}
  }
}

function add10(num) {
  return num + 10;
}

let addCache = createCache(add10, 'foo');

addCache(12); // 22
addCache(100); // 110
addCache(1); // 11

addCache('foo'); // {12: 22, 100: 110, 1: 11}
```

4. Change the above function in such a way that when the returned function is called with any other value than password. It should first check the object where we are storing the argument and return value. If the key is present return the value form the object itself. Otherwise call the callback function with the parameter.

```js
function createCache(cb, pwd) {
  let obj = {};
  return function(param){
  	if(param !== pwd){
  		if(obj[param]){
  			return obj[param];
  		}else{
				obj[param] = cb(param);
				return cb(param);
  		}	
  	}else{
  		return obj;
  	}
  }
}


function add10(num) {
  return num + 10;
}

let addCache = createCache(add10, 'foo');

addCache(12); // 22
addCache(100); // 110
addCache(100); // 110 (callback should not be called)
addCache(100); // 110 (callback should not be called)
addCache(1); // 11

addCache('foo'); // {12: 22, 100: 110, 1: 11}
```
