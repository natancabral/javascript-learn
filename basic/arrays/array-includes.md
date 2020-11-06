## Includes
#### The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate.

> Array.includes(find,startIndex);

```js
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// expected output: true

const pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// expected output: true

console.log(pets.includes('at'));
// expected output: false
```
#### Simple

```js
[1, 2, 3].includes(2)      // true
[1, 2, 3].includes(4)      // false
[1, 2, 3].includes(3, 3)   // false
[1, 2, 3].includes(3, -1)  // true
[1, 2, NaN].includes(NaN)  // true

```

#### startIndex || fromIndex

```js
let arr = ['a', 'b', 'c']

arr.includes('c', 3)    // false
arr.includes('c', 100)  // false
```

#### Negative Index

```js
let arr = ['a', 'b', 'c']

// array length is 3
// fromIndex is -100
// computed index is 3 + (-100) = -97

arr.includes('a', -100) // true
arr.includes('b', -100) // true
arr.includes('c', -100) // true
arr.includes('a', -2)   // false
```
