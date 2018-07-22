# Pipe to New File
`$ echo "Sample data" > ./my-new-file.txt`

# Pipe and Append to File
`$ echo "More Data" >> ./my-new-file.txt`

# Pipe stderr to stdout
`2>&1`

# Silence output
`$ redis-server > /dev/null`

# Silence stderr and stdout
`$ redis-server > /dev/null 2>&1`

# Append to end of file
# possibility 3:
`$ cat <<EOT >> greetings.txt`
line 1
line 2
EOT
