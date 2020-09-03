# NODE FILES

## Summary

Notes on working with files in Nodejs

## Resources

- [File System Flags](https://nodejs.org/api/fs.html#fs_file_system_flags)
- [Read File Line By Line](https://nodejs.org/api/readline.html#readline_example_read_file_stream_line_by_line)

## Get Buffer Instead Of Text

```javascript
fs.readFileSync(file)
```

## Get Text Instead Of Buffer

Have to specify encoding

```javascript
fs.readFileSync(file, 'utf-8');`
```

## Simple Stream Writing

```javascript
const opts = { flags: 'w+' }
const wstream = fs.createWriteStream('test.txt', opts)
const createDocs = (cnt = 0) => {
  for (let i = 0; i < cnt; i += 1) {
    wstream.write(JSON.stringify('hello'))
  }
  wstream.end()
}
createDocs(1)
```

## Simple Stream Reading

```javascript
const fs = require('fs')
const readline = require('readline')

async function processLineByLine() {
  const fileStream = fs.createReadStream('input.txt')
  const rl = readline.createInterface({
    input: fileStream,
    crlfDelay: Infinity,
  })
  // Note: we use the crlfDelay option to recognize all instances of CR LF
  // ('\r\n') in input.txt as a single line break.
  for await (const line of rl) {
    // Each line in input.txt will be successively available here as `line`.
    console.log(`Line from file: ${line}`)
  }
}
processLineByLine()
```

## Write A File To Disk

```javascript
fs.writeFileSync('data.json', JSON.stringify(data))
```

## Read And Write With JSON

Remember to `JSON.parse()` and then `JSON.stringify()`

```javascript
const fs = require('fs')
const file = fs.readFileSync('./my-file.json', 'utf-8') // without utf-8 you get a buffer
const records = JSON.parse(file)
const docs = records.docs.map((i) => ({ ...i, myNewProperty: 'test' }))
fs.writeFileSync('my-updated-file.json', JSON.stringify(docs))
```

## Append And Read Flags

```javascript
const opts = { flags: 'a+' }
```
