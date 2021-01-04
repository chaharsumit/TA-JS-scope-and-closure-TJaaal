1. Implement `forEach` array method using Array.reduce

```js
function forEach() {
  // Your code goes here
}

forEach(['Sam', 'Jon', 'Arya'], (name, i, arr) =>
  console.log(name + name, i, arr)
);
```

2. Implement `map` array method using Array.reduce

```js
function map() {
  // Your code goes here
}

map(['Sam', 'Jon', 'Arya'], (name) => name + name); // ['SamSam', 'JonJon', 'AryaArya']
```

3. Implement `filter` array method using Array.reduce

```js
function filter() {
  // Your code goes here
}
filter(['Sam', 'Jon', 'Arya'], (name) =>
  name.startsWith('S')
); // ['Sam']
```
