# NODE FILE TOOLS

## Summary

Notes on working with files in Nodejs

## Resources

[Read Really Large Files](https://itnext.io/using-node-js-to-read-really-really-large-files-pt-1-d2057fe76b33)

## Read Last Line Of File

[SO](https://stackoverflow.com/questions/40107433/read-last-line-of-a-large-file-with-nodejs)
// fileTools.js

```javascript
const fs = require("fs");
const readline = require("readline");
const Stream = require("stream");

exports.getLastLine = (fileName, minLength = 1) => {
  let inStream = fs.createReadStream(fileName);
  let outStream = new Stream();
  return new Promise((resolve, reject) => {
    let rl = readline.createInterface(inStream, outStream);

    let lastLine = "";
    rl.on("line", function(line) {
      if (line.length >= minLength) {
        lastLine = line;
      }
    });

    rl.on("error", reject);

    rl.on("close", function() {
      resolve(lastLine);
    });
  });
};
```
