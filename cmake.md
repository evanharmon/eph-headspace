# CMAKE

## Summary

Notes on using CMake

## Auto generate `compile_commands.json`

in CMakeLists.txt

```txt
cmake_minimum_required (VERSION 2.6)
project (Tutorial)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
add_executable(person Person.cc Pirate.cc main.cc)
```

### Export CMAKE Variable

```console
export DCMAKE_EXPORT_COMPILE_COMMANDS=1
```

### Build With Debug Symbols

```txt
set(CMAKE_BUILD_TYPE Debug)
```
