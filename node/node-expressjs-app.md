# NODE EXPRESSJS APP

## Attach Database Connections to app
makes db connection available on `req.app.get('db')` or `req.app.settings.db`
# single connection created
`app.set('db',new MyDAO(config))`

## new connection per request
```
app.use((req, res, next) => {
    req.db = db; //this db comes from app.js context where you define it
    next();
});
```
