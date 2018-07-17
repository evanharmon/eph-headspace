# Woff files not loading correctly
Make sure you are allowing for adjustments after the filename such as
"icomoon.woff?5km1tg" in your test loader
`/\.(woff)(\?\S*)/`
as in the below
`{ test: /\.(eot|woff|woff2|ttf|svg|png|jpe?g|gif)(\?\S*)?$/, loader: 'url-loader'}`

# Font Awesome
```
import 'font-awesome/css/font-awesome.css';

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
