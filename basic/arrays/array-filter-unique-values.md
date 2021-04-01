## Unique Values (Filter/From/Set/Map)
> return New Array() | .filter(value, index, self) | .from(array, callback(value, index)) | new Set(Array)

#### Classic | ES5
```js
function onlyUnique(value, index, self) {
  return self.indexOf(value) === index;
}
// usage example:
var a = ['a', 1, 'a', 2, '1'];
var unique = a.filter(onlyUnique);
console.log(unique); 
// unique ['a', 1, 2, '1']
```

#### Best | ES6

```js
const myArray = ['a', 1, 'a', 2, '1'];
let unique = myArray.filter((value, index, self) => self.indexOf(value) === index);
console.log(unique); 
// unique is ['a', 1, 2, '1']
```

#### Fast

> ES6 has a native object Set to store unique values. To get an array with unique values you could do now this:

```js
var myArray = ['a', 1, 'a', 2, '1'];
let unique = [...new Set(myArray)];
console.log(unique); 
// unique ['a', 1, 2, '1']
```

#### Array.from() / A copy array

```js
var items = [4,5,4,6,3,4,5,2,23,1,4,4,4];
var uniqueItems = Array.from(new Set(items));
console.log(uniqueItens);
// [4,5,6,3,2,23,1]
```

## Unique Values | Object

```js
// Object Array
const listOfTags = [
    { id: 1, label: "Hello", color: "red", sorting: 0 }, 
    { id: 2, label: "World", color: "green", sorting: 1 }, 
    { id: 3, label: "Hello", color: "blue", sorting: 4 }, 
    { id: 3, label: "Hello id 3", color: "blue id 3", sorting: 4 }, 
    { id: 4, label: "Sunshine", color: "yellow", sorting: 5 }, 
    { id: 5, label: "Hello", color: "red", sorting: 6 }
];
// filter keys
const keys = ['label', 'color'];
// Action
const filtered = listOfTags.filter(
  (s => o => 
    (k => !s.has(k) && s.add(k))
      (keys.map(k => o[k]).join('|'))
    )
    (new Set)
  );
console.log(filtered);
```

Solution #2 (one key comparison)
```js
const property = 'id';
const filtered = listOfTags.reduce((acc, current) => {
  const x = acc.find(item => item[property] === current[property]);
  if (!x) {
    return acc.concat([current]);
  } else {
    return acc;
  }
}, []);
console.log(filtered);
```

Solution #3 (one key comparison)
```js
const property = 'id';
const seen = new Set();
const filtered = listOfTags.filter(el => {
  const duplicate = seen.has(el[property]);
  seen.add(el[property]);
  return !duplicate;
});
console.log(filtered);
```

Solution #4 (one key comparison)
```js
const property = 'id';
const filtered = [...new Map(listOfTags.map(item => [item[property], item])).values()];
console.log(filtered);
```
