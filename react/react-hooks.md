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
