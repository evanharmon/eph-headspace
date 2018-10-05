# NODE FILE

## Get Buffer Instead Of Text
`fs.readFileSync(file);`

## Get Text Instead Of Buffer
Have to specify encoding
`fs.readFileSync(file, 'utf-8');`

## Simple Stream Writing
```
const opts = { flags: 'w+' };
const wstream = fs.createWriteStream('test.txt', opts);
const createDocs = (cnt = 0) => {
  for (let i = 0; i < cnt; i += 1) {
  wstream.write(JSON.stringify('hello'));
  }
  wstream.end();
};
createDocs(1);
```

## Write A File To Disk
`fs.writeFileSync('data.json', JSON.stringify(data));`

## Read And Write With JSON
Remember to `JSON.parse()` and then `JSON.stringify()`
```javascript
const fs = require('fs');
const file = fs.readFileSync('./my-file.json', 'utf-8'); // without utf-8 you get a buffer
const records = JSON.parse(file);
const docs = records.docs.map(i => ({ ...i, myNewProperty: 'test' }));
fs.writeFileSync('my-updated-file.json', JSON.stringify(docs));
```
