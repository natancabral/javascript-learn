
## Arrow functions

#### Comparing traditional functions to arrow functions

```js
// Traditional Function
function (a){
  return a + 100;
}

// Arrow Function Break Down

// 1. Remove the word "function" and place arrow between the argument and opening body bracket
(a) => {
  return a + 100;
}

// 2. Remove the body brackets and word "return" -- the return is implied.
(a) => a + 100;

// 3. Remove the argument parentheses
a => a + 100;
```

#### Two arguments

```
// Traditional Function
function (a, b){
  return a + b + 100;
}

// Arrow Function
(a, b) => a + b + 100;

// Traditional Function (no arguments)
let a = 4;
let b = 2;
function fun(){ 
  return a + b + 100;
}
let result = fun(); 

// Arrow Function (no arguments)
let a = 4;
let b = 2;
let result = () => a + b + 100;
```

```js
// Traditional Function
function (a, b){
  let chuck = 42;
  return a + b + chuck;
}
 
// Arrow Function
(a, b) => {
  let chuck = 42;
  return a + b + chuck;
}
```

```js
// Traditional Function
function bob (a){
  return a + 100;
}

// Arrow Function
let bob = a => a + 100;
bob(110);
// 210
```
