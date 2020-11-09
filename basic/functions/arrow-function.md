
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

```js
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

#### Variable function | React.js Class

```js
// tradicional function js
function name (v) {
}
// function jsx
name(v){
}
// to react class 
name = (v) => {
}
```

#### Break lines

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

#### Named functions

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

## Advanced syntax

#### To return an object literal expression requires parentheses around expression:

```js
params => ({foo: "a"}) // returning the object {foo: "a"}
```

#### Rest parameters are supported:

```js
(a, b, ...r) => expression
```

#### Default parameters are supported:

```js
(a=400, b=20, c) => expression
```

#### Destructuring within params supported:

```js
// Aray
([a, b] = [10, 20]) => a + b;  // result is 30
// Object
({ a, b } = { a: 10, b: 20 }) => a + b; // result is 30
```

#### Sample

```js
// Object
const book = {
  id: 1,
  name: 'Book Name',
} 
// Object
const person = {}
person.id = 1;
person.name = 'First Name';
person.lastName = 'Last Name';

// Old 
let idBook = book.id
let nameBook = book.name
// New Catch 
const {id, name} = book;
console.log(name) // Book Name
const {lastName, name, id } = person;
console.log(lastName) // Last Name
```
