# HTML CANVAS

## Summary
Notes on using HTML5 canvas element

## Resources

## Rotate around a centerpoint
- [Canvas Transformations and Gradients](http://code.tutsplus.com/tutorials/canvas-from-scratch-transformations-and-gradients--net-19637)

```javascript
context.save(); // saves the coordinate system
context.translate(250,50); // now the position (0,0) is found at (250,50)
context.rotate(0.30); // rotate around the start point of your line
context.moveTo(0,0) // this will actually be (250,50) in relation to the upper left corner
context.lineTo(0,200) // (250,250)
context.stroke();
context.restore(); // restores the coordinate system back to (0,0)
```


## Scale Canvas Width / Height to Client Device
- [Canvas size & WebGL](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Canvas_size_and_WebGL)
- [Hi DPI Canvas](https://www.html5rocks.com/en/tutorials/canvas/hidpi/)

```javascript
const dpr = window.devicePixelRatio || 1
canvas.width = canvas.clientWidth * dpr
canvas.height = canvas.clientWidth * dpr
const ctx = canvas.getContext('2d')
ctx.scale(dpr, dpr)
```

## Pass Canvas To Function
```javascript
const ctx = canvasRef.getContext('2d')
myFunction(ctx.canvas)
```
