## Find

#### The find() method returns the value of the first element in the provided array that satisfies the provided testing function.

```js
const array1 = [5, 12, 8, 130, 44];
const found = array1.find(element => element > 10);
console.log(found);
// expected output: 12
```

#### Find an object in an array by one of its properties

```js
const inventory = [
  {name: 'apples', quantity: 2},
  {name: 'bananas', quantity: 0},
  {name: 'cherries', quantity: 5}
];

function isCherries(fruit) { 
  return fruit.name === 'cherries';
}

console.log(inventory.find(isCherries)); 
// { name: 'cherries', quantity: 5 }
```

#### Using arrow function and destructuring

```js
const inventory = [
  {name: 'apples', quantity: 2},
  {name: 'bananas', quantity: 0},
  {name: 'cherries', quantity: 5}
];
const result = inventory.find( (arr) => arr.name === 'cherries' );
//or better:
const result = inventory.find( ({ name }) => name === 'cherries' );
console.log(result) // { name: 'cherries', quantity: 5 }
```
