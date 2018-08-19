# CSS GRID

## Display Values
`display: grid`
`display: inline-grid`
`display: subgrid`

## Gutter
`grid-gap: 5px;`

## Ordering For Small Screens
grid-template-areas:
     "header"
     "section"
     "aside-1"
     "aside-2"
     "footer";

## Larger Screen Ordering
```
@media (min-width: 700px) {
     .container {
          grid-template-areas:
               "header header header"
               "aside-1 section aside-2"
               "footer footer footer";
     }
}
```
## Columns
`grid-template-columns: 100px 200px auto auto;`

## Start A Column Further To Right
```
.grid-item:nth-of-type(6) {
     grid-column-start: 3;
}
```

## Span Column Across Multiple Columns
```
.grid-item:nth-of-type(6) {
     grid-column-start: 3;
     grid-column-end: 5;
}
```
