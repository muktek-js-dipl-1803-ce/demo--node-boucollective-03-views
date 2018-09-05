# demo--node-boucollective-03-views

### Preconfiguration

Install ejs

```
npm install --save ejs
```

### Files Modified

**(A)** `server.js`
  + import ejs
  + configure ejs

  ```js
  // Part.3.A.1 - Import EJS 
  const ejs = require('ejs')
    
  //....

  // Part.3.A.1 - Configure EJS as the application
  //              view engine
  
  app.engine( 'ejs', ejs.renderFile )
  app.set('view engine', 'ejs')
  app.set('views', `${__dirname}/src/views`)

  app.use('/api', apiRouter)
  app.use('/', pageRouter)

  //....
  ```

**(B)** `pageRouter.js`
  + use `res.render()`
  
  ```js
  pageRouter
  .get('/', (req, res)=>{
    // Part.3.B.1 - res.render to send .ejs files from `/views`
    res.render('home.ejs', { copyright: currentYear})
  })


  pageRouter
    .get('/about', (req, res)=>{
      res.render('about.ejs')
  })
  ```
