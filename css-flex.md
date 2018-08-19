# CSS FLEX
Cheat Sheet Websites
(https://yoksel.github.io/flex-cheatsheet/)
(https://benweiser.com/making-flexbox-less-scary/)

## Unordered Lists
## have to apply flex properties
```
ul {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
```

## Take up additional space / fill horizontal / fill screen
`flex-grow: 1;`

## Flex Scope inheritance
This means that a flex container is always the parent and a flex item is always
the child. Flex properties work only within this relationship

Descendants of a flex container beyond the children are not part of flex layout
and will not accept flex properties. Essentially, elements that are descendants
of flex items do not inherit flex properties

## Align items along bottom
`align-items: flex end`

## Flex Shorthand
flex: <flex-grow> <flex-shrink> <flex-basis>;
```
.column {
  flex: 1 1 0px;
}
```
