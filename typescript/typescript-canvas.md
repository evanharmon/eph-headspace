# TYPESCRIPT Canvas

## Summary
Notes on using the html5 canvas api with typescript

## Resources

## requestAnimationFrame
support requestAnimationFrame cross-browser types

declarations.d.ts, then add to tsconfig
```typescript
// designate browser context
export {}

declare global {
    interface Window {
        webkitRequestAnimationFrame: typeof requestAnimationFrame
        mozRequestAnimationFrame: typeof requestAnimationFrame
    }
}
```

index.tsx
```typescript
declare global {
    const requestAnimFrame: typeof requestAnimationFrame
}

const requestAnimFrame = (() => window.requestAnimationFrame || window.webkitRequestAnimationFrame || window.mozRequestAnimationFrame)()
```
