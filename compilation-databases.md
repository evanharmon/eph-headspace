# COMPILATION DATABASES

## Summary

Notes on working with compilation databases

## Resources

[Introduction](http://eli.thegreenplace.net/2014/05/21/compilation-databases-for-clang-based-tools)

## Ninja

generate compilation database with `ninja`

```console
ninja -t compdb cxx > compile_commands.json
```
