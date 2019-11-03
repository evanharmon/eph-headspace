# JUCE FILES

## Summary

Notes on using the juce framework with files

## Resources

## Argument Parsing

arguments MUST have an equal sign `--file=myfile.txt`

## VST Plug-Ins Not Building

common errors:

- cannot find `vstfxstore.h` [Forums](https://forum.juce.com/t/plugininterfaces-vst2-x-vstfxstore-h-not-found/30301/2)

set preprocessor flag `JUCE_VST3_CAN_REPLACE_VST2=0` in your projucer
configuration under `Preprocessor Definitions`
