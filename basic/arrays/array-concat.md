## Concat 
> return New Array() | .concat(array2, array3, ..., arrayX)
#### Concatenate arrays
```js
const hege = ["Cecilie", "Lone"];
const stale = ["Emil", "Tobias", "Linus"];

let children = hege.concat(stale);
//or
let children = [].concat(hege,stale);
//or
let children = [...hege, ...stale];

console.log(children);
// ["Cecilie", "Lone", "Emil", "Tobias", "Linus"]
```
#### Spread Merge EC6
```js
let children = [...hege, ...stale];
// ["Cecilie", "Lone", "Emil", "Tobias", "Linus"]
```
#### Sample 1 [].
```js
const isArray = [1, 2, 3];
const notArray = 'random';

let result = [...isArray, ...noArray);
// [ 1, 2, 3, 'r', 'a', 'n', 'd', 'o', 'm' ]

let result = [].concat(isArray, noArray);
// [ 1, 2, 3, 'random' ] // Fine

```
#### Sample 2 - Push
```js
const cars = ['ford', 'ferrari'];
const trucks = ['mercedes', 'scania'];

cars.push(trucks);
// [ 'ford', 'ferrari', ['mercedes', 'scania'] ]

cars.push(...trucks);
// [ 'ford', 'ferrari', 'mercedes', 'scania' ]
```
