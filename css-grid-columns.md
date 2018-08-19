# CSS GRID COLUMNS

## HTML
```
<div className="container">
  <aside>Note List</aside>
  <section>Note Text</section>
</div>
```

## CSS
```
.container {
  display: grid;
  grid-gap: 5px;
  height: 100vh;
  width: 100vw;
  grid-template-columns: 30vw auto;
}

.container > * {
  background-color: mediumseagreen;
}
```
