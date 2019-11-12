# JUCE BUFFERS

## Summary

Notes on using buffers with the juce framework

## Resources

## Initialize Audio Buffer

```cpp
AudioBuffer<float> outputBuffer;
outputBuffer.setSize(2, 44100);
```
