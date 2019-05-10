# FONT AWESOME

## Summary

Notes on working with font awesome icon library

## Resources

[Accessibility](https://fontawesome.com/how-to-use/on-the-web/other-topics/accessibility)

## Accessibility

best practice for working with aria: use aria-hidden="true" and aria-label

```html
<a aria-label="Delete" class="btn btn-danger" href="path/to/settings">
  <i aria-hidden="true" class="fas fa-trash" title="Delete this item?"></i>
</a>
```
