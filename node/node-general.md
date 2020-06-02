# NODE

## Console Log Messages Not Working in Tests?
Try requiring the file in to the current testing file

## Editing Tests No Affect
If you are changing anything in node_modules, you must restart the terminal
session because it is cache'ing!

## Testing Buffers
`Buffer.isBuffer(obj)`

## Testing Encoding
`Buffer.isEncoding(obj)`

## Check byte length
`Buffer.byteLength(str, encoding);`

## Base64
`new Buffer('this is a string', 'ascii').toString('base64');`

## Write File Sync
no callback - nothing returned
`fs.writeFileSync("filename/path", data);`

## Write File to String
Include encoding type
`const txt = fs.readFileSync("filename/path", "utf-8")`

## Write Object to File
```
const str = JSON.stringify(object);
fs.WriteFileSync("./test/filename.json", str);
```

## Log Entire Object
```
const { inspect } = require('util')
console.log(inspect(myObject, {showHidden: false, depth: null}))
// alternative shortcut
console.log(inspect(myObject, false, null))
```

## Get Byte Size of String
```
function getBytes(string){
  return Buffer.byteLength(string, 'utf8')
}
```

# Exit with failure code
`process.exit(1);`
