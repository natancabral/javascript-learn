## Delete
### Array()
> return Array()
#### Delete = Undefined
> **Warning**: Doesn't like delete myArray[0] syntax saying "Expected an operator and instead saw 'delete'." Using splice is recommende.
```js
let myArray = ['a', 'b', 'c', 'd']
// ["a", "b", "c", "d"]
delete myArray[0];
// true
myArray[0];
// undefined
console.log(myArray);
// [empty, "b", "c", "d"]
// [undefined, "b", "c", "d"]
// Index positon don't removed
```
#### Splice
```js
arr // [0, 1, 2, 3, 4]
arr.splice(3,1); // 3
arr // [0, 1, 2, 4]
```
#### Sample 1
```js
// first element removed
someArray.shift();
someArray.splice(0, 1);
someArray = someArray.slice(1); // slice create a New Array()

// last element removed
someArray.pop();
someArray.splice(-1, 1);
someArray = someArray.slice(0, a.length - 1); // slice create a New Array()
someArray.length = someArray.length - 1;
```
en: If you want to remove element at position x, use:
```js
someArray.splice(x, 1);
```
#### Splice with While
```js
let items = ['a', 'b', 'c', 'd', 'a', 'b', 'c', 'd'];
while (items.indexOf('c') !== -1) {
  items.splice(items.indexOf('c'), 1);
}
console.log(items); 
// ["a", "b", "d", "a", "b", "d"]
```
#### Remove One Item Function
```js
function removeItemOnce(arr, value) {
  var index = arr.indexOf(value);
  if (index > -1) {
    arr.splice(index, 1);
  }
  return arr;
}
//Usage
let arr = [2,5,9,1,5,8,5];
console.log(removeItemOnce(arr, 5))
// remove one 5
// [2,9,1,5,8,5]
```
#### Remove All Itens Function
```js
function removeItemAll(arr, value) {
  var i = 0;
  while (i < arr.length) {
    if (arr[i] === value) {
      arr.splice(i, 1);
    } else {
      ++i;
    }
  }
  return arr;
}
//Usage
let arr = [2,5,9,1,5,8,5];
console.log(removeItemAll(arr, 5))
// remove all 5
// [2,9,1,8]
```
#### Create Remove on Prototype
```js
/ Array Remove - By John Resig (MIT Licensed)
Array.prototype.remove = function(from, to) {
  var rest = this.slice((to || from) + 1 || this.length);
  this.length = from < 0 ? this.length + from : from;
  return this.push.apply(this, rest);
};
```
en: And here's some examples of how it could be used:
```js
// Remove the second item from the array
array.remove(1);
// Remove the second-to-last item from the array
array.remove(-2);
// Remove the second and third items from the array
array.remove(1,2);
// Remove the last and second-to-last items from the array
array.remove(-2,-1);
```
[John's website](http://ejohn.org/blog/javascript-array-remove/)
### Object()
> return Object()
#### Remove Property
```js
var myObject = {
    "ircEvent": "PRIVMSG",
    "method": "newURI",
    "regex": "^http://.*"
};

delete myObject.regex;
// or,
delete myObject['regex'];
// or,
var prop = "regex";
delete myObject[prop];

console.log(myObject);
// {
//    "ircEvent": "PRIVMSG",
//    "method": "newURI",
// };
```
