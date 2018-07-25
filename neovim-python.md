# NEOVIM PYTHON
(https://neovim.io/doc/user/nvim_python.html)

## Check Python in Neovim
`:python print 1`
`:py print sys.version`

## Check Python Version Detected in Neovim
`:let [interp, errors] = provider#pythonx#Detect(2)  " Can also be used to check for Python 3.`
`:echo interp  " If empty, Neovim didn't find a suitable Python interpreter.`
`:echo errors  " Shows which Python interpreters Neovim checked.`
