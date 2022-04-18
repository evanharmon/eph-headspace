# CHROME CONSOLE

## Copy object
```javascript
copy($($0).scope().address);
```

## Shortcut document.querySelector()
```javascript
$()
```

## Shortcut document.querySelectorAll()
```javascript
$$()
```

## Five Recent DOM Elements
```javascript
$0 - $4
```

## Print out entire function text
while paused for debugging
```javascript
functionName.toString()
```

## Group Console Logs
```javascript
for (var i = 0; i < 100; i++) {
    const num = Math.random() * 100;
    console.group('picking a random number");
    console.log('number greater than 10', num > 10);
    console.log('number greater than 50', num > 50);
    console.groupEnd();
}
```

## Console Logging Types
```javascript
console.log()
console.warn()
console.error()
console.info()
console.debug()
```

## Console Log Timing Events
```javascript
console.time('createObjects');
let array = [];
for (var i = 0; i < 1000000; i++) {
    array.push({ index: i });
}

console.timeEnd('createObjects');
```

## Console Log Pretty Print Tabular Data
```javascript
function Character(name, power) {
    this.name = name;
    this.power = power;
}

const buffy = new Character('buffy', 'slayer');
const willow = new Character('willow' ,'witch');
const spike = new Character('spike', 'vampire');

const chars = [buffy, willow, spike];

console.table(chars);
```

## Fetch with custom headers
```javascript
const request = new Request('https://apiendpoint/test/?id=1234', {
  method: 'GET',
  mode: 'cors',
  redirect: 'follow',
  headers: new Headers({
    'Content-Type': 'application/json',
    'custom-key': 'xxxxxxxx'
  })
});
fetch(request).then(res => console.log(res));
```
