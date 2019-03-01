# CSS FLEX

Cheat Sheet Websites
(https://yoksel.github.io/flex-cheatsheet/)
(https://benweiser.com/making-flexbox-less-scary/)

## Summary

Notes on using flex box with CSS

## Do's

- use to arrange items inside a container either horizontally or vertically

## Dont's

- don't use flex box to try and do the layout for an entire web page

## Unordered Lists

have to apply flex properties

```css
ul {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
```

## Take up additional space / fill horizontal / fill screen

```css
flex-grow: 1;
```

## Flex Scope inheritance

This means that a flex container is always the parent and a flex item is always
the child. Flex properties work only within this relationship

Descendants of a flex container beyond the children are not part of flex layout
and will not accept flex properties. Essentially, elements that are descendants
of flex items do not inherit flex properties

## Align items along bottom

```css
align-items: flex end;
```

## Flex Shorthand

```css
flex: <flex-grow> <flex-shrink> <flex-basis>;
```

```css
.column {
  flex: 1 1 0px;
}
```
