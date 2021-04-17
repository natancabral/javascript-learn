## Currying Functions

#### Currying is an advanced technique of working with functions. It’s used not only in JavaScript, but in other languages as well.

```js
function curry( fn ) {
  return function( a ) {
    return function( b ) {
      return fn( a, b );
    };
  };
}

// usage
function sum( a, b ) {
  return a + b;
}

const value = curry( sum )( 1 )( 2 );
console.log( value ); 
// result: 3
```

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
