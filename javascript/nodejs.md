
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


