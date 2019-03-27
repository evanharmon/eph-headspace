# PYTHON HEX

## Summary

Notes on working with hex in python

## Read Binary File And Print As Hex

[SO](https://stackoverflow.com/questions/34687516/how-to-read-binary-files-as-hex-in-python)

```python
import binascii

with open('data.geno', 'rb') as f:
    hexdata = binascii.hexlify(f.read())
```
