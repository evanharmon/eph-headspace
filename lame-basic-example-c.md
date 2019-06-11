#define DR_WAV_IMPLEMENTATION
#include <stdio.h>
#include <lame/lame.h>

int main(int argc, char *argv[])
{
    int read;
    int write;

    FILE *pcm = fopen(argv[1], "rb");
    fseek(pcm, 44, 0); // skip header, super hacky right now

    FILE *mp3 = fopen("file.mp3", "wb");

    const int PCM_SIZE = 8192;
    const int MP3_SIZE = 8192;

    short int pcm_buffer[PCM_SIZE*2];
    unsigned char mp3_buffer[MP3_SIZE];

    lame_t lame = lame_init();
    lame_set_num_channels(lame, 2);
    lame_set_in_samplerate(lame, 48000);
    lame_set_VBR(lame, vbr_off); // CBR mode
    lame_set_brate(lame, 320);
    lame_init_params(lame);
    lame_print_config(lame);

    do {
        read = fread(pcm_buffer, 2*sizeof(short int), PCM_SIZE, pcm);
        printf("%i\n", read);
        if (read == 0)
            write = lame_encode_flush(lame, mp3_buffer, MP3_SIZE);
        else
            write = lame_encode_buffer_interleaved(lame, pcm_buffer, read, mp3_buffer, MP3_SIZE);
        fwrite(mp3_buffer, write, 1, mp3);
    } while (read != 0);

    lame_close(lame);
    fclose(mp3);
    fclose(pcm);

    return 0;
}
