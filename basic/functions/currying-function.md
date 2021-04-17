## Currying Functions

#### Comparing traditional functions to curryimng functions

```js
// Traditional Function
function toStringfy( ...fn ){
  return function( string ) {
     // reduce fn
  };
}

const value = toStringfy( fn )(' Welcome to JS Currying and Lazy Evaluation');
console.log( value );
// result
```

#### Lazy Evaluation

```js
cons lazy = ( string, fn ) => {
  read: function (){
    return //map 
  },
  getIndex: function( index ){
    return //map 
  },
  removeIndex: function( index ){
    return //map 
  },
}
const value = lazy( "Weolcome", s => s.toUpperCase() ).getIndex(2);
console.log( value );
// result
```

#### Lazy Evaluation

```js
cons lazy = ( arr, fn ) => {
  read: function (){
    return //map 
  },
  getIndex: function( index ){
    return //map 
  },
  removeIndex: function( index ){
    return //map 
  },
}

const value = lazy( [1,2,3,4,5], x => x*2 ).getIndex(2);
console.log( value );
// result
```
