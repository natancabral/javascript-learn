## Map
> return New Array()

```js
let newArray = arr.map(callback(currentValue[, index[, current array]]) {
  // return element for newArray, after executing something
}[, thisArg]);
```

#### Log
```js
[4,5,6,7].map((a,b,c)=>console.log(a,b,c))
//[4,5,6,7].map((currentValue,index,currentArray)=>console.log(currentValue,index,currentArray))

//console.log(a,b,c)
// 4,  0,  Array(4) [ 4, 5, 6, 7 ]
// 5,  1,  Array(4) [ 4, 5, 6, 7 ]
// 6,  2,  Array(4) [ 4, 5, 6, 7 ]
// 7,  3,  Array(4) [ 4, 5, 6, 7 ]
```

#### Example

```js
const array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(function(x){ return x * 2 });
const map1 = array1.map((x) => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
```

#### Object Key

```js
let kvArray = [{key: 1, value: 10}, 
               {key: 2, value: 20}, 
               {key: 3, value: 30}]

let reformattedArray = kvArray.map(obj => {
   let rObj = {}
   rObj[obj.key] = obj.value
   return rObj
})
// reformattedArray is now [{1: 10}, {2: 20}, {3: 30}], 

// kvArray is still: 
// [{key: 1, value: 10}, 
//  {key: 2, value: 20}, 
//  {key: 3, value: 30}]
```
```js
let numbers = [1, 4, 9]
let doubles = numbers.map(function(num) {
  return num * 2
})

// doubles is now   [2, 8, 18]
// numbers is still [1, 4, 9]
```

#### Simple Map

```js
// Same as above, but using the concise arrow function syntax
['1', '2', '3'].map( str => parseInt(str) )
// A simpler way to achieve the above, while avoiding the "gotcha":
['1', '2', '3'].map(Number)  // [1, 2, 3]
// But unlike parseInt(), Number() will also return a float or (resolved) exponential notation:
['1.1', '2.2e2', '3e300'].map(Number)  // [1.1, 220, 3e+300]
// For comparison, if we use parseInt() on the array above:
['1.1', '2.2e2', '3e300'].map( str => parseInt(str) ) // [1, 2, 3]
```
#### Map with Index

```js
let numbers = [1, 2, 3, 4]
let filteredNumbers = numbers.map(function(num, index) {
  if (index < 3) {
     return num
  }
})
// ndex goes from 0, so the filterNumbers are 1,2,3 and undefined.
// filteredNumbers is [1, 2, 3, undefined]
// numbers is still [1, 2, 3, 4]
```
