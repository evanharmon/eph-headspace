# Loader vs Loaders
Loader is for single strings. Loaders is for array of strings

# Loader Order
right to left when a string
bottom to top when an array
`loaders:['style', 'css']`

# HTML-loader Ignore attrs like img
## can cause module not found errors
`{ test: /\.html$/, use: 'html-loader?attrs=false' }`

# File-loader
## load files as hashes
`use: 'file-loader?name=[hash:6].[ext]'`
