# ALE

## Summary

Notes on using the `ale` plugin in neovim / vim

## Resources

- [GITHUB](https://github.com/dense-analysis/ale)

## CLANGD COMPILATION DATABASE SUPPORT

assuming typical `./build` directory for cmake / ninja

```
let g:ale_cpp_clangd_options='-compile-commands-dir=build'
```
