# HTML CANVAS

## Rotate around a centerpoint
(http://code.tutsplus.com/tutorials/canvas-from-scratch-transformations-and-gradients--net-19637)
context.save(); // saves the coordinate system
context.translate(250,50); // now the position (0,0) is found at (250,50)
context.rotate(0.30); // rotate around the start point of your line
context.moveTo(0,0) // this will actually be (250,50) in relation to the upper left corner
context.lineTo(0,200) // (250,250)
context.stroke();
context.restore(); // restores the coordinate system back to (0,0)
