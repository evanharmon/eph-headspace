# test: /regex/
A condition may be a RegExp (tested against absolute path), a string containing
the absolute path, a function(absPath): bool, or an array of one of these
combined with “and”

# Match file extension exactly
## $ is exact match! This won't match JSX
`test: /\.js$/`

# Match multiple extensions endings
## This will match both .js and .jsx files
`test: /\.js?/`

# Match multiple file extensions exactly
`test: /\.(js|jsx)$/,`
