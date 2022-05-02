# REACT HOOKS

## Summary

Notes on using react hooks useEffect

## Resources

## When To UseEffect

A useEffect is for making indirect function calls as a side-effect of another function.

example when a useEffect is not needed. All functions can be run directly as a
result of the click event

```tsx
function myComponent = () => {
  const onClickHandler = () => {
    if (playing === false) {
      const clip = new Clip(audioEngine, audioBuffer)
      clip?.node?.connect(audioEngine.destination)
      clip?.play(0)
      setClip(clip)
      setPlaying(true)
    } else {
      clip?.stop(0)
      setPlaying(false)
    }
  }

  return (
    <section className='tape'>
      <audio src='outfoxing.mp3' crossOrigin='anonymous'></audio>
      <button
        className='tape-controls-play'
        data-playing={playing ?? false}
        role='switch'
        aria-checked='false'
        onClick={onClickHandler}
      >
        <span>Play/Pause</span>
      </button>
    </section>
  )
}
```

### useState re-renders

look for opportunities to pass useState a function for any expensive computations that dont need to run on every re-render.
DO NOT use this lazy initialization of state for cheap computations bc it will actually be slower.

### useRef

- retain pointer to a value between renders
- look for values that when changed shouldn't trigger re-render

### useMemo

- cache expensive computations
- avoids a useEffect call for sideeffect

example:

```tsx
const filesLoaded = useMemo(() => {
  // code here
  return true || false
}, [filesToLoad, files])
```

### useCallback

- prevent unnecessary re-renders

### useLayoutEffect

sync: blocks browser paint
If you need to mutate the DOM and/or do need to perform measurements
for dom mutations that should happen before paint to avoid a 'flicker' or value flip
