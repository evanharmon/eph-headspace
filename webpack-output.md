# output filename
# only affects output bundles not require.ensures
# must NOT be an absolute path
`output: { filename: '[name].[chunkhash].js' }`

# output path MUST be an absolute path
`output: { path: path.join(__dirname, 'app/dist/') }`

# public path for s3 static site use
`output: { path: path.join(__dirname, 'app/dist/') }`
