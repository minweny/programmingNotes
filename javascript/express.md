https://expressjs.com/en/guide/routing.html     

## Routing      
app.method, handle post requests    
app.use, specify middleware as the callback function    
next, calls the next callback function    

```
var express = require('express')
var router = express.Router()

// middleware that is specific to this router
router.use(function timeLog (req, res, next) {
  console.log('Time: ', Date.now())
  next()
})
// define the home page route
router.get('/', function (req, res) {
  res.send('Birds home page')
})
// define the about route
router.get('/about', function (req, res) {
  res.send('About birds')
})

module.exports = router
```



