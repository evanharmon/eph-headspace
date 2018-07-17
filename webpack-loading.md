# WEBPACK LOADING
## Loader vs Loaders
Loader is for single strings. Loaders is for array of strings

## Loader Order
right to left when a string
bottom to top when an array
`loaders:['style', 'css']`

## HTML-loader
Ignore attrs like img. Can cause module not found errors
`{ test: /\.html$/, use: 'html-loader?attrs=false' }`

## File-loader
load files as hashes
`use: 'file-loader?name=[hash:6].[ext]'`

## Make lodash available globally
Remember to add as a global to .eslint
`{ test: /lodash/, loader: 'exports?_'}`

## test: /regex/
A condition may be a RegExp (tested against absolute path), a string containing
the absolute path, a function(absPath): bool, or an array of one of these
combined with “and”

## Match file extension exactly
$ is exact match! This won't match JSX
`test: /\.js$/`

## Match multiple extensions endings
This will match both .js and .jsx files
`test: /\.js?/`

## Match multiple file extensions exactly
`test: /\.(js|jsx)$/,`

## IMAGES / ICONS
### Woff files not loading correctly
Make sure you are allowing for adjustments after the filename such as
"icomoon.woff?5km1tg" in your test loader
`/\.(woff)(\?\S*)/`
as in the below
`{ test: /\.(eot|woff|woff2|ttf|svg|png|jpe?g|gif)(\?\S*)?$/, loader: 'url-loader'}`

### Font Awesome
In jsx file:
```
import 'font-awesome/css/font-awesome.css';
```
In webpack config:
```
rules: [
      {
        test: /\.css$/,
        use: ExtractTextPlugin.extract({
          fallback: 'style-loader',
          use: [
            { loader: 'css-loader' },
          ],
        }),
      },
      {
        test: /\.(eot|svg|ttf|woff(2)?)(\?v=\d+\.\d+\.\d+)?/,
        loader: 'url-loader',
      },
]
```
