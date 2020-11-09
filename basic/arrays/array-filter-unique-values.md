## Unique Values (Filter/From)
> return New Array() | .filter(value, index, self) | .from(array, callback(value, index))

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

#### Dont Works

```js
//Dont works from Object
const v = [{a:11},{a:22},{a:33},{a:22},];
Array.from(new Set(v),(x,i,y) => console.log(x,i))
Object { a: 11 }
Object { a: 22 }
Object { a: 33 }
Object { a: 22 }

//Works but only one value
const person = [ 
  {"name":"Joe", "age":17}, 
  {"name":"Bob", "age":17}, 
  {"name":"Tom", "age":35} 
];
// Set Unique Values
const ages = [...new Set(person.map(x => x.age))]
console.log(ages)
// [17,35]
```
