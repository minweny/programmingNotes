
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


