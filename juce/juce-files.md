# JUCE FILES

## Summary

Notes on using the juce framework with files

## Resources

## Files

## Basic Reading From Audio File

[Forums](https://forum.juce.com/t/as-a-newbie-i-just-want-to-load-a-sample-and-play-it/24108/7)

```cpp
AudioSampleBuffer outputBuffer;
String path = "someFile.wav";
int64 sourceStartSample = 0;
int numReadSamples = 512;

File soundFile = File(path);
AudioFormatManager manager;
manager.registerBasicFormats();
AudioFormatReader* reader = manager.createReaderFor(soundFile);
outputBuffer.setSize((int)reader->numChannels, (int)reader->lengthInSamples);
reader->read(&outputBuffer, 0, jmin((int)reader->lengthInSamples, numReadSamples), sourceStartSample, true, true);
```

## Basic Writing To Audio File

[Forums](https://forum.juce.com/t/write-a-wav-file-from-buffer-example/31789)
[Roli GH](https://github.com/WeAreROLI/JUCE/blob/master/examples/Audio/AudioRecordingDemo.h#L87)

```cpp
AudioBuffer<float> buffer;
WavAudioFormat format;
std::unique_ptr<AudioFormatWriter> writer;
writer.reset (format.createWriterFor (new FileOutputStream (file),
                                      48000.0,
                                      buffer.getNumChannels(),
                                      24,
                                      {},
                                      0));
if (writer != nullptr)
    writer->writeFromAudioSampleBuffer (buffer, 0, buffer.getNumSamples());
```

or

```
void writeToFile(AudioBuffer<float> buffer, File outFile, lengthInSamples) {
  const String outFileExt = outFile.getFileExtension();
  AudioFormat *fmtType = manager.findFormatForFileExtension(outFileExt);
  AudioFormatWriter *writer =
      fmtType->createWriterFor(new FileOutputStream(outFile), 44100,
                               buffer.getNumSamples(), 24, {}, 0);
  writer->writeFromAudioSampleBuffer(buffer, 0, lengthInSamples);
  writer->flush();
  delete writer;
}
```

### Load Buffer From File

```cpp
void loadBuffer()
{
    AudioFormatManager formatManager;
    formatManager.registerBasicFormats();
    std::unique_ptr<AudioFormatReader> reader (formatManager.createReaderFor(File("/Users/nammick/Desktop/Dump/test.wav")));
    // NB: you really must check for a nullptr here
    buffer.setSize((int)reader->numChannels, (int)reader->lengthInSamples);
    reader->read(&buffer, 0,(int)reader->lengthInSamples,0, true,true);
}
```

### Save To File From Buffer

```cpp
void saveOutput()
{
    File outputFile("/Users/nammick/Desktop/analysis1.wav");
    auto outStream = outputFile.createOutputStream();
    // in real code you must check whether the stream is null before continuing
    WavAudioFormat format;
    std::unique_ptr<AudioFormatWriter> writer (format->createWriterFor(outStream, 44100, output.getNumChannels(), 32,nullptr, 0));
    // again, you need add a check for a nullptr here
    writer->writeFromAudioSampleBuffer(output, 0, output.getNumSamples());
}
```
