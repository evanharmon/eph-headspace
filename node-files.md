# NODE FILE

## Get Buffer Instead of Text
`fs.readFileSync(file);`

## Get text instead of buffer
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

## Write a file to disk
`fs.writeFileSync('data.json', JSON.stringify(data));`
