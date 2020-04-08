# COC SNIPPETS

## Summary

Notes on using snippets with COC in neovim

## Resources

- [GH](https://github.com/neoclide/coc-snippets)

### Support React

add to `~/.config/nvim/coc-settings.json`

```json
"snippets.extends": {
  "cpp": ["c"],
  "javascriptreact": ["javascript"],
  "typescript": ["typescript"]
},
```

### Support vim-go

add to `~/.config/nvim/coc-settings.json`

```json
snippets.ultisnips.directories: [
  "UltiSnips",
  "gosnippets/UltiSnips"
],
```

### Add Custom Snippets

add snippet files to `$VIMCONFIG/coc/ultisnips`

### Edit Snippets For Filetype

in neovim run `:CocCommand snippets.editSnippets`
