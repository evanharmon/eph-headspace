# TYPESCRIPT WEBAUDIO

## Summary
Notes on using the webaudio api with typescript

## Resources

## WebKitAudio
support webkitAudioContext cross-browser types

declarations.d.ts, then add to tsconfig
```typescript
// designate browser context
export {}

declare global {
    interface Window {
        webkitAudioContext: typeof AudioContext
        mozAudioContext: typeof AudioContext
    }
}
```

index.tsx
```typescript
declare global {
  const audioContext: AudioContext
}

const audioContext = (() => window.webkitAudioContext || window.AudioContext || window.mozAudioContext)()
```
