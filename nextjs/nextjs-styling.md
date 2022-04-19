# NEXTJS STYLING

## Resources

- [Nextjs CSS Docs](https://nextjs.org/docs/basic-features/built-in-css-support)

## Global Styling in Components

way to style base elements like `body` outside `styles/globals.css`

```jsx
return (
  <>
    <style global jsx>{`
      body {
        font-family: 'Times';
      }
    `}</style>
  </>
)
```
