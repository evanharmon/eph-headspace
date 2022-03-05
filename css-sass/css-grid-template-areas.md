# CSS GRID TEMPLATE AREAS

## HTML
```
<div className="container">
  <header>Header</header>
  <aside>Note List</aside>
  <section>Note Text</section>
  <footer>Footer</footer>
</div>
```

## CSS
```
.container {
  display: grid;
  grid-gap: 5px;
  height: 100vh;
  grid-template-areas:
  "header"
  "section"
  "aside"
  "footer"
}

.container > * {
  background-color: mediumseagreen;
}

header {
  grid-area: header;
}

aside {
  grid-area: aside;
}

section {
  grid-area: section;
}

footer {
  grid-area: footer;
}

@media (min-width: 700px) {
  .container {
  grid-template-areas:
  "header header header header"
  "aside section section section"
  "footer footer footer footer"
  }
}
```
