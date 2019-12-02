# COMPILATION DATABASES

## Summary

Notes on working with compilation databases

## Resources

[Introduction](http://eli.thegreenplace.net/2014/05/21/compilation-databases-for-clang-based-tools)
[Clang Setup](https://clang.llvm.org/docs/HowToSetupToolingForLLVM.html)

## Neovim

[Vimrc setup](https://clang.llvm.org/docs/HowToSetupToolingForLLVM.html)

## CMAKE Clang Create Compilation Database

Run below command from directory that contains `CMakeLists.txt`

```console
cmake -G Ninja -DCMAKE_EXPORT_COMPILE_COMMANDS=ON -DCMAKE_C_COMPILER=/usr/bin/clang -DC_MAKE_CXX_COMPILER=/usr/bin/clang++ .
```

## Ninja

note: this does not seem to be working for me - use the `cmake` style above
generate compilation database with `ninja`

```console
ninja -t compdb cxx > compile_commands.json
```
