# NEOVIM NEOSNIPPET

## For Neosnippet conceal markers - also hides json quotes which is annoying!
```
" if has('conceal')
  " set conceallevel=2 concealcursor=niv
" endif
```

## Supertab like behavior
```
" SuperTab like snippets behavior.
"imap <expr><TAB>
" \ pumvisible() ? "\<C-n>" :
" \ neosnippet#expandable_or_jumpable() ?
" \ "\<Plug>(neosnippet_expand_or_jump)" : "\<TAB>"
smap <expr><TAB> neosnippet#expandable_or_jumpable() ?
\ "\<Plug>(neosnippet_expand_or_jump)" : "\<TAB>"
```
