# Require file from another chunk / module with .ensure
```
require.ensure([
  '../services/media/mymedia.media.svc'
], (obj) => {
  let MyMediaService = obj;
});
```
