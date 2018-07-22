# Find Command
[Tutorial](https://www.digitalocean.com/community/tutorials/how-to-use-find-and-locate-to-search-for-files-on-a-linux-vps)

# Search for filename recursively
## . means current directory, asterix is important bc it's not regex partial match like grep
`$ find . -name "login*"`

# Find by date time by Days
## Access Time -atime
## Modification Time -mtime
Change Time -ctime
`$ find ./ -mtime 1`

Less than a day
`$ find ./ -ctime -1`

Find by date time by Minutes
`$ find ./ -mmin -1`

# List # of folders in a sub-folder
`$ find ./folder-name -mindepth 1 -maxdepth 1 -type d | wc -l`

# Rename files with regex
## use brew install rename
Removing spaces
`$ find ./ -name "* *" -type f | rename 's/ /_/g'`

# Find files above size
`$ find /usr -size +1M`
