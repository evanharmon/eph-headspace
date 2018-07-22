# Linter with line position of suggestions
http://www.shellcheck.net

# Run and execute commands from current shell enviroment
`$ source ./script.sh`

# Pass argument from script call to variable inside script
```
$ sh stats.sh songlist
$ FILE1=$1
$ wc $FILE1
```

# Run script in new shell
`$ ./script.sh`

# Assign Variable
`$ a=879`

# Assign Path to Variable
`$ VF=./container-files/vim-7.4.tar.bz2`

# Assign Command to a Variable
`$ a=`ls -la``

# WGET
`$ VIM_URL=ftp://ftp.vim.org/pub/vim/unix/vim-7.4.tar.bz2`
`$ wget "$VIM_URL"`

# Reference Current Directory
`${PWD}`

# Script error unary operator expected
Double quote your variables!
`"$IP"`

# Abort on first error
#!/bin/bash
set -e

/bin/command-that-fails
/bin/command-that-fails2

# Single Quote Double Quote in Scripts
http://mywiki.wooledge.org/Quotes

# Find and replace in a file from shell command
`$ sed -i 's/REPLACE_WITH_INSTANCE_IP/'$INSTANCE_IP'/g' /tmp/init-cluster.sh`

# Get base name of a file from full path
`$ basename /home/user/file.sh`

# Check if folder exists and remove
DIR=/tmp/dir.lock
if [ -d "$DIR" ]; then
    printf '%s\n' "Removing Lock ($DIR)"
    rm -rf "$DIR"
fi
