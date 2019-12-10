# COC

## Summary

Notes on using COC in neovim

## Resources

- [Github](https://github.com/neoclide/coc.nvim)
- [Language Servers Wiki](https://github.com/neoclide/coc.nvim/wiki/Language-servers)

## CLANGD Setup

with typical `./build` directory for cmake / ninja

```json
{
  "languageserver": {
    "clangd": {
      "command": "clangd",
      "args": ["--background-index -compile-commands-dir=build"],
      "rootPatterns": [
        "compile_flags.txt",
        "compile_commands.json",
        "build/compile_commands.json",
        ".vim/",
        ".git/",
        ".hg/"
      ],
      "filetypes": ["c", "cpp", "objc", "objcpp"]
    }
  }
}
```
