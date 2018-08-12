# NODE DOT ENV

## Reference .env config file by exact path
```
const path = require('path');
require('dotenv').config({ path: path.join(__dirname, '.env') }); // eslint-disable-line global-require
```
