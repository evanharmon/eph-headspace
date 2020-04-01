# WAV FILES

## Summary

Info on the different formats of WAV files

## Resources

- [Guide](http://soundfile.sapp.org/doc/WaveFormat/)

### Header Size

Starts at byte 45

### Data Representation - 24bit vs 32bit

- [SO](https://stackoverflow.com/questions/24151973/reading-24-bit-samples-from-a-wav-file)

```
~ ~ ~ ~ ~ ~ ~ ~ ~ ~ MSB ~ ~ 2ndMSB ~ ~ 2ndLSB ~ ~ LSB ~ ~

24-bit sample: 11001101 01101001 01011100 00000000

32-bit sample: 11001101 01101001 01011100 00101001
```
