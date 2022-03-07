# DR-WAV

## Summary

Notes on using the dr_wav.h header only implementation file for interacting
with wav files

## Resources

- [GH](https://github.com/mackron/dr_libs/blob/master/dr_wav.h)

## My Examples

required outer code for each example

```c
#define DR_WAV_IMPLEMENTATION
#include <stdio.h>
#include "dr_wav.h"

const int CHUNK_SIZE = 8192;
const int BIT_FORMAT = 32;
const float frames_to_read = CHUNK_SIZE / BIT_FORMAT;
```

## Read PCM Data In Chunks

edited code and untested

```c
int main(int argc, char *argv[])
{
    int read;

    drwav wav;
    if (!drwav_init_file(&wav, argv[1])) {
        printf("Failed to open file");
        return -1;
    }

    float pcm_buffer[CHUNK_SIZE*wav.channels];

    do {
        read = drwav_read_pcm_frames_f32(&wav, frames_to_read, pcm_buffer);
        if (read == 0)
            // do something like flush a buffer
        else
            // do something with the frames read
    } while (read == frames_to_read);

    drwav_uninit(&wav);

    return 0;
}
```

## Doc Examples

```c
s is a single-file library. To use it, do something like the following in one .c file.
    #define DR_WAV_IMPLEMENTATION
    #include "dr_wav.h"

You can then #include this file in other parts of the program as you would with any other header file. Do something
like the following to read audio data:

    drwav wav;
    if (!drwav_init_file(&wav, "my_song.wav")) {
        // Error opening WAV file.
    }

    drwav_int32* pDecodedInterleavedSamples = malloc(wav.totalPCMFrameCount * wav.channels * sizeof(drwav_int32));
    size_t numberOfSamplesActuallyDecoded = drwav_read_pcm_frames_s32(&wav, wav.totalPCMFrameCount, pDecodedInterleavedSamples);

    ...

    drwav_uninit(&wav);

You can also use drwav_open() to allocate and initialize the loader for you:

    drwav* pWav = drwav_open_file("my_song.wav");
    if (pWav == NULL) {
        // Error opening WAV file.
    }

    ...

    drwav_close(pWav);

If you just want to quickly open and read the audio data in a single operation you can do something like this:

    unsigned int channels;
    unsigned int sampleRate;
    drwav_uint64 totalPCMFrameCount;
    float* pSampleData = drwav_open_file_and_read_pcm_frames_f32("my_song.wav", &channels, &sampleRate, &totalPCMFrameCount);
    if (pSampleData == NULL) {
        // Error opening and reading WAV file.
    }

    ...

    drwav_free(pSampleData);

The examples above use versions of the API that convert the audio data to a consistent format (32-bit signed PCM, in
this case), but you can still output the audio data in its internal format (see notes below for supported formats):

    size_t samplesRead = drwav_read_pcm_frames(&wav, wav.totalPCMFrameCount, pDecodedInterleavedSamples);

You can also read the raw bytes of audio data, which could be useful if dr_wav does not have native support for
a particular data format:

    size_t bytesRead = drwav_read_raw(&wav, bytesToRead, pRawDataBuffer);


dr_wav can also be used to output WAV files. This does not currently support compressed formats. To use this, look at
drwav_open_write(), drwav_open_file_write(), etc. Use drwav_write_pcm_frames() to write samples, or drwav_write_raw()
to write raw data in the "data" chunk.

    drwav_data_format format;
    format.container = drwav_container_riff;     // <-- drwav_container_riff = normal WAV files, drwav_container_w64 = Sony Wave64.
    format.format = DR_WAVE_FORMAT_PCM;          // <-- Any of the DR_WAVE_FORMAT_* codes.
    format.channels = 2;
    format.sampleRate = 44100;
    format.bitsPerSample = 16;
    drwav* pWav = drwav_open_file_write("data/recording.wav", &format);

    ...

    drwav_uint64 samplesWritten = drwav_write_pcm_frames(pWav, frameCount, pSamples);
```
