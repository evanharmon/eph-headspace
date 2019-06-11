# LAME

## Summary

Notes on using the c api for Lame for mp3 encoding / decoding

## Install Via Yum

```console
yum install -y lame-devel
```

## Set Constant Bit Rate To 320

[SO](https://stackoverflow.com/questions/35151284/lame-increase-bitrate-to-320)

```c
lame_t lame = lame_init();
lame_set_in_samplerate(lame, 48000);
lame_set_VBR(lame, vbr_off); // CBR mode
lame_set_brate(lame, 320);
lame_init_params(lame);
```

## Print Config

```c
lame_print_config(lame);
```

## Reading From WAV File

example:
fread(buffer, 4, 8192, pcmfile)
read = 8192 bytes read

```c
FILE *pcm = fopen(argv[1], "rb");
fseek(pcm, 44, 0); // skip header
const int PCM_SIZE = 8192;
short int pcm_buffer[PCM_SIZE*2]; // buffer size * 2 for stereo, representing a FRAME
read = fread(pcm_buffer, 2*sizeof(short int), PCM_SIZE, pcm);
```
