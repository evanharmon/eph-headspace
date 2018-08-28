# NEOVIM PYTHON
(https://neovim.io/doc/user/nvim_python.html)

## Check Python In Neovim
```
:python print 1
:py print sys.version
```

## Check Python Version Detected In Neovim
`:let [interp, errors] = provider#pythonx#Detect(2)`

## Check Neovim Python Intrerpreter
`:echo interp`

## Show Which Python Interpreters Neovim Checked
`:echo errors`
