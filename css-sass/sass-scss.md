# SASS

## Summary
Notes on using SASS and the SCSS syntax

## Resources

- [Docs](https://sass-lang.com/documentation)

## Only top level SCSS files need to be compiled
### Otherwise you'll see errors such as Undefined Variable: $

## all variables need to be provided as imports
### Otherwise you'll see errors such as Undefined Variable: $
`@import 'angular-material/angular-material.scss';`

## Ignore Url's
### really it's to get CSS-loader to ignore the URls with absolute path
```sass
@font-face {
    font-family: 'icomoon';
    src:url('/assets/icons/fonts/icomoon.woff');
}
```

## Variable


```scss
$base-color: #c6538c;
```
