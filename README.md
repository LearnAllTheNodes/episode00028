# Learn All The Nodes Episode 28

## Making values available to all views

[View the episode](http://www.learnallthenodes.com/episodes/28-making-values-available-to-all-views)


### Notes

[Opening clipart](http://openclipart.org/detail/562/matrioshka-by-artefact)

[Crypto](http://nodejs.org/api/crypto.html)

[Accounting.js](https://github.com/openexchangerates/accounting.js)

[Express `app.locals` documentation](http://expressjs.com/4x/api.html#app.locals)

[Episode code](http://www.learnallthenodes.com/episodes/28-making-values-available-to-all-views)

    // At init time
    app.locals.crypto = require('crypto')
    
    // A middleware for values that change with each request
    function attachReq(req,res,next) {
      res.locals.req = req
      res.locals.util = require('util')
      next()
    }
    app.use(attachReq)
