## Unique Values
> return New Array()

## Classic | ES5
```js
function onlyUnique(value, index, self) {
  return self.indexOf(value) === index;
}
// usage example:
var a = ['a', 1, 'a', 2, '1'];
var unique = a.filter(onlyUnique);
console.log(unique); 
// ['a', 1, 2, '1']
```

## Best | ES6

```js
const myArray = ['a', 1, 'a', 2, '1'];
let unique = myArray.filter((value, index, self) => self.indexOf(value) === index);
console.log(unique); 
// unique is ['a', 1, 2, '1']
```
