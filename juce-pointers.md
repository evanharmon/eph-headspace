# JUCE POINTERS

## Summary

Notes on working with pointers in JUCE

## Resources

- [Forum: Getting Rid of ScopedPointer](https://forum.juce.com/t/getting-rid-of-scopedpointer/33725)

## Converting ScopedPointer Legacy Code

old ScopedPointer

```cpp
addAndMakeVisible( m_label = new MyLabel( "Label" ) );
```

replace with unique_ptr

```cpp
m_label = std::make_unique<MyLabel> ("Label");
addAndMakeVisible (*m_label);
```

if part of a class and private

```cpp
std::unique_ptr<MyLabel> m_label;
```
