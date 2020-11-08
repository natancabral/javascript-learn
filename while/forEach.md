## forEach (***Unrecommended***)
> Better [Map](/while/map.md)
#### The forEach() method executes a provided function once for each array element.

```js
const array1 = ['a', 'b', 'c'];
array1.forEach(element => console.log(element));

// expected output: "a"
// expected output: "b"
// expected output: "c"

```

#### forEach expects a synchronous function

> **Warning:** forEach does not wait for promises. Kindly make sure you are aware of the implications while using promises(or async functions) as forEach callback. Example Code

> **Warning:** There is no way to stop or break a forEach() loop other than by throwing an exception. If you need such behavior, the forEach() method is the wrong tool.

```js
let ratings = [5, 4, 5];
let sum = 0;

let sumFunction = async function (a, b){
  return a + b
}

ratings.forEach(async function(rating) {
  sum = await sumFunction(sum, rating)
})

console.log(sum)
// Naively expected output: 14
// Actual output: 0
```

## 

```js
const arraySparse = [1,3,,7]
let numCallbackRuns = 0

arraySparse.forEach((element) => {
  console.log(element)
  numCallbackRuns++
})

console.log("numCallbackRuns: ", numCallbackRuns)
// 1
// 3
// 7
// numCallbackRuns: 3
// comment: as you can see the missing value between 3 and 7 didn't invoke callback function.
```

#### Loop

```js
const items = ['item1', 'item2', 'item3']
const copyItems = []

// before
for (let i = 0; i < items.length; i++) {
  copyItems.push(items[i])
}

// after
items.forEach(function(item){
  copyItems.push(item)
})
```

