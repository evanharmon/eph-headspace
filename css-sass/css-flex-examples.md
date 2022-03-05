# CSS FLEX EXAMPLES

## HTML
```
<ul class="flex-container">
  <li class="flex-item header">Header</li>
  <li class="flex-item sidebar">Sidebar</li>
  <li class="flex-item main">Main</li>
  <li class="flex-item sidebar">Sidebar</li>
  <li class="flex-item footer">Footer</li>
</ul>
```

## CSS
```
.flex-container {
  padding: 0;
  margin: 0;
  list-style: none;
  height: 200px;
  display: flex;

  justify-content: space-around;
  flex-flow: row wrap;
  align-items: stretch;
}

.header,
.footer  { flex: 1 100%; }
.sidebar { flex: 1; }
.main    { flex: 2; }

.flex-item {
  background: tomato;
  padding: 10px;
  width: 100px;
  border: 3px solid rgba(0,0,0,.2);

  color: white;
  font-weight: bold;
  font-size: 2em;
  text-align: center;
}
```
