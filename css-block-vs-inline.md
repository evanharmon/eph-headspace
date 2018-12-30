# CSS BLOCK LEVEL / IN-LINE

## Summary
Block Level vs In-line Elements

## Display
makes block level and inline level elements behave the same
Height and Width now determined by container

```css
display: inline-block;
```

## Block
- elements always start on new-line
- width of element is 100% of container
- height determined by content

ex:
```html
  <div>my div</div>
  <p>my paragraph.</p>
```

```css
div, p {
  background: red;
  height: 50px;
  width: 200px;
}
```

## Customize Height / Width
use height and width properties

#### Block Nesting
- can nest block or in-line elements

#### Force Block Elements As In-Line
Height and Width now determined by content

```css
div, p {
  background: red;
  height: 50px;
  width: 200px;
  display: inline;
}
```

## In-Line
- elements height / width determined by content: aka text in a <span />

ex:
```html
<span>my span</span>
<a href="#">My Link.</a>
```

```css
span, a {
  background: grey;
  height: 40px; // no effect by default
  width: 150px; // no effect by default
}
```

#### In-Line Nesting
- should only nest other in-line elements (except anchor / span tags)
- elements align left in a line by default
- by default, height and width properties have no effect


#### Force In-Line Elements As Block
Height now determined by container not content

```css
span, a {
  background: grey;
  height: 40px;
  width: 150px;
  display: block;
}
```
#### Force In-Line Elements As In-Line And Block
Elements now In-Line next to each other
Height and Width now determined by container not content

```css
span, a {
  background: grey;
  height: 40px;
  width: 150px;
  display: block;
}
```


## Center Align Elements

```css
display: inline-block;
text-align:center;
```

## Center Align with Margin

```css
margin: auto;
```


## Check If An Element Is Block or In-Line
- wrap element in a background-color or border-style
- block elements will have the color / style across the whole width of screen
- in-line elements color / style will only be as wide as the content
