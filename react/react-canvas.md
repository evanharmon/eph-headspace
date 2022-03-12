# REACT CANVAS

## Summary
Notes on using canvas with react and react refs

## Resources
- [React Canvas Audio Analyser](https://javascript.plainenglish.io/canvas-animation-inside-react-components-with-requestanimationframe-c5d594afc1b)


# Hook Example
Notes:
- add canvas html in component and useRef
- create animation requestId useRef
- create empty useLayoutEffect hook
- create empty animate and renderFrame functions
- create requestAnimationFrame utilizing requestIdRef and animate function
- update requestIdRef on every animate function call
- exit early from animate call if no canvasref created yet
- add placeholder call in animate function to renderFrame

ignoring webkit / mozilla browser diffs on requestAnimationFrame
```tsx
export default function AudioAnalyzer() {
    const canvasRef = useRef<HTMLCanvasElement | null(null)
    const requestIdRef = useRef<number>()

    const renderFrame = () => {

    }

    useLayoutEffect(() => {
        const animate = () => {
          if (!canvasRef.current) return

          renderFrame()
          requestIdRef.current = requestAnimationFrame(animate)
        }
        requestIdRef.current = requestAnimationFrame(animate)
        return () => {
          if (requestIdRef.current) cancelAnimationFrame(requestIdRef.current)
        }
    }, [])
    
    return (
      <>
        <canvas ref={canvasRef} width="512" height="256"/>
      </>
    )
}
```
