# NPM SCRIPTS

## Use NODE_ENV environment variables
`"start": "NODE_ENV=${NODE_ENV:-development} node index"`

## Run Tests as TEST
`"test": "NODE_ENV=test ./node_modules/.bin/mocha test"`
