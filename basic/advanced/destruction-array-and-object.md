## Destruction Array & Object
> return Array | Object
#### Object destructuring // Based on the key
```js
const person = {
  name: 'Mike',
  lastname: 'Jordan', // key lowercase
  age: 23,
  address: {
    city: 'Las Vegas',
    state: 'Nevada'
  }
}

const {name, age} = person;
console.log(name); // Mike
console.log(age); // 23

const {name : firstname, age} = person;
console.log(name); // Undefined
console.log(firstname); // Mike
console.log(age); // 23

const {name : firstname, age = 11} = person;
console.log(age); // 23 -> No change

const {name : firstname, age, ...rest} = person;
console.log(rest); // 
//  address: {
//    city: 'Las Vegas',
//    state: 'Nevada'
//  }

const {name : firstname, age, address: { street } } = person;
console.log(street); // Undefined 

const {name : firstname, age, address: { city } } = person;
console.log(city); // Las Vegas 
```
#### Inside Functions Inside Arguments
```js
// Old
function printUser(pers){
  console.log(`My name is ${pers.name}, age is ${pers.age}`.);
}
printUser(person);
// My name is Jordan, age is 23.

// New {} | Select keys
function printUser({ name, age }){
  console.log(`My name is ${name}, age is ${age}`.);
}
printUser(person);
// My name is Jordan, age is 23.
```

#### Inside Functions Inside Arguments
```js
// No change information
function printUser({ name = 'Billie', age = 20 }){
  console.log(`My name is ${name}, age is ${age}`.);
}
printUser(person);
// No change Object
// My name is Jordan, age is 23. 
```
