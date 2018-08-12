# NODE KOAJS

## Attach a DB Function to App
Inside index.js / start file
```
app.use(function* (next) {
     this.db = app.db;
     yield next;
}
```

## Mount library
(https://github.com/koajs/mount)

## Mount entire koa middleware applications at specific paths
`app.use(mount('/hello', hello));`

## Mount middleware with Koa-router
```
const router = koaRouter();
app.use("/dashboard", router.middleware());
```

## Route Library
(https://github.com/alexmingoia/koa-router)

## This Use
request, response, body, etc are attached to this object
```
this.body = <html></html>;
this.type = "html";
this.request.body.email = newEmail;
this.status = 400;
```
