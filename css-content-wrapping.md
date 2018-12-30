# CSS CONTENT WRAPPING

## Summary
Notes on using a CSS content wrapper class

## Width
Width is fixed so in a content wrapper it will create a scroll bar on shrinking
window

Max-width enforces wrapping as the content stays to 100% of container
```css
Max-width: 950px;
```

## Container Spacing

#### Remove Extra Spacing On Container
Wrong way to do it:

```css
h2, p {
  margin: 0;
}
```
This removes space between container but makes the content too close to the edge
and squished

Right way to do it:

Instead add padding to container element content wrapper. This will remove extra
spacing too

```css
.content-wrapper {
 width: 950px;
 margin: 0 auto;
 padding: 50px;
}
```

#### Remove Extra Spacing On Body
Remove default body margin around whole page
```css
body {
  margin: 0;
}
```
