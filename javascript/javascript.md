
## Chrome to Editor     
```
document.body.contentEditable = true;
```

## export module    
https://www.tutorialsteacher.com/nodejs/nodejs-module-exports   
```
The following example exposes simple string message as a module in Message.js.

Message.js Copy
module.exports = 'Hello world';

//or

exports = 'Hello world';
Now, import this message module and use it as shown below.

app.js Copy
var msg = require('./Messages.js');

console.log(msg);

```

## MEAN   
MEAN is an acronym for MongoDB, ExpressJS, AngularJS, and Node.js.    

## Strange result: null vs 0    
https://javascript.info/comparison      
Let’s compare null with a zero:     
```
alert( null > 0 );  // (1) false
alert( null == 0 ); // (2) false
alert( null >= 0 ); // (3) true
```
Mathematically, that’s strange. The last result states that "null is greater than or equal to zero", so in one of the comparisons above it must be true, but they are both false.

The reason is that an equality check == and comparisons > < >= <= work differently. Comparisons convert null to a number, treating it as 0. That’s why (3) null >= 0 is true and (1) null > 0 is false.

On the other hand, the equality check == for undefined and null is defined such that, without any conversions, they equal each other and don’t equal anything else. That’s why (2) null == 0 is false.

## callback     
function called as argument     

## Function Expression vs Function Declaration      
function declaration available in the same block        

## There are 8 basic data types in JavaScript.    
- number for numbers of any kind: integer or floating-point, integers are limited by ±253.
- bigint is for integer numbers of arbitrary length.
- string for strings. A string may have zero or more characters, there’s no separate single-character type.
- boolean for true/false.
- null for unknown values – a standalone type that has a single value null.
- undefined for unassigned values – a standalone type that has a single value undefined.
- object for more complex data structures.
- symbol for unique identifiers.

## A double NOT !! is sometimes used for converting a value to boolean type:        
```
alert( !!"non-empty string" ); // true
alert( !!null ); // false
```

## The nullish coalescing operator ?? provides a short syntax for selecting a first “defined” variable from the list.

The result of a ?? b is:

a if it’s not null or undefined,
b, otherwise.
So, x = a ?? b is a short equivalent to:

x = (a !== null && a !== undefined) ? a : b;

|| returns the first truthy value.      
?? returns the first defined value.

## A function that is the property of an object is called its method.       

## Method shorthand     
```
// these objects do the same

user = {
  sayHi: function() {
    alert("Hello");
  }
};

// method shorthand looks better, right?
user = {
  sayHi() { // same as "sayHi: function()"
    alert("Hello");
  }
};
```

## “this” is not bound      
In JavaScript, keyword this behaves unlike most other programming languages. It can be used in any function.

The value of this is evaluated during the run-time, depending on the context.       

## Arrow functions have no “this”
Arrow functions are special: they don’t have their “own” this. If we reference this from such a function, it’s taken from the outer “normal” function.

For instance, here arrow() uses this from the outer user.sayHi() method:
```
let user = {
  firstName: "Ilya",
  sayHi() {
    let arrow = () => alert(this.firstName);
    arrow();
  }
};

user.sayHi(); // Ilya
```

## Constructor function     
```
function User(name) {
  // this = {};  (implicitly)

  // add properties to this
  this.name = name;
  this.isAdmin = false;

  // return this;  (implicitly)
}

```

## optional chaining        
```
let user = {}; // user has no address

alert( user?.address?.street ); // undefined (no error)

let user1 = {
  admin() {
    alert("I am admin");
  }
}

let user2 = {};

user1.admin?.(); // I am admin
user2.admin?.();
```

## To loop over the elements of the array:

- for (let i=0; i<arr.length; i++) – works fastest, old-browser-compatible.
- for (let item of arr) – the modern syntax for items only,
- for (let i in arr) – never use.

## The “arguments” variable     
There is also a special array-like object named arguments that contains all arguments by their index.
```
For instance:

function showName() {
  alert( arguments.length );
  alert( arguments[0] );
  alert( arguments[1] );

  // it's iterable
  // for(let arg of arguments) alert(arg);
}

// shows: 2, Julius, Caesar
showName("Julius", "Caesar");

// shows: 1, Ilya, undefined (no second argument)
showName("Ilya");
```

## array/object copy        
```
let arr = [1, 2, 3];
let arrCopy = [...arr]; // spread the array into a list of parameters
                        // then put the result into a new array

let obj = { a: 1, b: 2, c: 3 };
let objCopy = { ...obj }; // spread the object into a list of parameters
                          // then return the result in a new object
```

## Decorator        
Decorator is a wrapper around a function that alters its behavior.

## func.call
There’s a special built-in function method func.call(context, …args) that allows to call a function explicitly setting this.

The syntax is:

func.call(context, arg1, arg2, ...)
It runs func providing the first argument as this, and the next as the arguments.





