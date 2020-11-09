## Array.from() / Shalow-Copied

> return New Array() | Array.from(Array, callBack(value,index) ) 

#### Basic
```js
console.log(Array.from('foo'));
// expected output: Array ["f", "o", "o"]

console.log(Array.from([1, 2, 3], x => x + x));
// expected output: Array [2, 4, 6]

Array.from([11,22,33],(x,i,y) => console.log(x, x*2, i))
// 11, 22, 0 
// 22, 44, 1
// 33, 66, 2
```

#### Array from a String

```js
Array.from('foo'); 
// [ "f", "o", "o" ]
```

#### Array from a Set

```js
const set = new Set(['foo', 'bar', 'baz', 'foo']);
Array.from(set);
// [ "foo", "bar", "baz" ]
```

#### Array from a Map

```js
const map = new Map([[1, 2], [2, 4], [4, 8]]);
Array.from(map);
// [[1, 2], [2, 4], [4, 8]]

const mapper = new Map([['1', 'a'], ['2', 'b']]);
Array.from(mapper.values());
// ['a', 'b'];

Array.from(mapper.keys());
// ['1', '2'];
```

#### Array from a NodeList

```js
// Create an array based on a property of DOM Elements 
const images = document.getElementsByTagName('img'); 
const sources = Array.from(images, image => image.src);
const insecureSources = sources.filter(link => link.startsWith('http://'));
```

#### Array from an Array-like object (arguments)

```js
function f() {
  return Array.from(arguments);
}

f(1, 2, 3);

// [ 1, 2, 3 ]
```

#### Using arrow functions and Array.from()

```js
// Using an arrow function as the map function to
// manipulate the elements
Array.from([1, 2, 3], x => x + x);      
// [2, 4, 6]

// Generate a sequence of numbers
// Since the array is initialized with `undefined` on each position,
// the value of `v` below will be `undefined`
Array.from({length: 5}, (v, i) => i);
// [0, 1, 2, 3, 4]
```
