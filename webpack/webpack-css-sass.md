# WEBPACK CSS / SASS
## Process Sass
```
module: {
    loaders: [
        {test: /\.js$/, exclude: /node_modules/, loader: 'babel'},
        {test: /\.scss$/, loader: ExtractTextPlugin.extract('css!sass')}
    ]
},
plugins: [
    new ExtractTextPlugin("style.css")
]
```

## Working SASS for src:url images
```
module.exports = {
    entry: {
        app: './js/bootstrap'
    },

    output: {
        filename: 'bundle.js',
        path: 'dist',
        publicPath: 'dist/'
    },

    module: {
        loaders: [
            {
                test: /\.scss$/,
                loader: ExtractPlugin.extract('style', 'css!sass')
            },
            {
                test: /\.(gif|png|svg|jpe?g)$/i,
                loader: 'url',
                query: {
                    limit: 1000
                }
            }
        ]
    },

    resolve: {
        // add alias for application code directory
        alias:{
            js: path.resolve(__dirname, 'js'),
            styles: path.resolve(__dirname, 'styles'),
            images: path.resolve(__dirname, 'images')
        },
        extensions: ['', '.js', '.scss', '.png', '.svg', '.jpg', '.jpeg', '.gif']
    }
};
```

## Create Two Separate Bundles
```
const extractVendor = new ExtractTextPlugin('vendor.css');
const extractApp = new ExtractTextPlugin('app.css');

    module: {
        rules: [
               {
                    test: /\.css$/,
                    use: extractVendor.extract({
                         fallback: 'style-loader',
                         use: [
                              { loader: 'css-loader',
                                   options: {
                                   }
                              }
                         ]
                    }),
                    exclude: path.resolve(__dirname, 'node_modules', 'angular-material', 'layouts')
               },
               {
                    test: /\.css$/,
                    use: extractApp.extract({
                         fallback: 'style-loader',
                         use: [
                              { loader: 'css-loader',
                                   options: {
                                   }
                              }
                         ]
                    }),
                    include: path.resolve(__dirname, 'node_modules', 'angular-material', 'layouts'),
               },
               { test: /\.scss$/,
                    loader: extractApp.extract({
                         fallback: 'style-loader',
                         use: [
                              { loader: 'css-loader',
                                   options: {
                                        importLoaders: 1
                                   }
                              },
                              { loader: 'postcss-loader',
                                   options: {
                                        plugins: function () {
                                             return [ AutoPrefixer ]
                                        }
                                   }
                              },
                              { loader: 'sass-loader',
                                   options: { includePaths: [path.resolve(PATHS.src), path.resolve(__dirname, 'node_modules')]}
                              }
                         ]
                    })
               },
    plugins: [
          extractVendor,
          extractApp,
    ]
```

## Use URL-loader and default to file-loader below certain size
```
{
  test: /\.(eot|svg|ttf|png|jpg|woff(2)?)(\?v=\d+\.\d+\.\d+)?/,
  use: 'url-loader?limit=1000',
},
```

```
import TF from '../assets/img/ThomasFitzsimmons-320x240.jpg';

const Artwork = () => (
  <div className="content-container">
    <div className="grid-container">
      <img src={TF} className="piece-medium" alt="Thomas Fitzsimmons on canvas" />
    </div>
  </div>
);
```

## Use in CSS / SASS file
relative to sass file location in directories
```
.scrollpic:nth-of-type(2) {
  background-image: url('assets/img/ThomasFitzsimmons.jpg')
}
```

## Use in HTML
can also do import or require up top
```
const Artwork = () => (
  <div className="content-container">
    <div className="grid-container">
      <img src={require('../assets/img/ThomasFitzsimmons-320x240.jpg')} className="piece-medium" alt="Thomas Fitzsimmons on canvas" />
    </div>
  </div>
);
```

## Include a font file
```
@font-face {
    font-family: 'Roboto';
    src: url('/assets/fonts/Roboto-Regular.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
}
```
## stop minification
had to set all defaults to false...
```
{ loader: 'postcss-loader',
     options: {
          plugins: function () {
               return [
                    require('cssnano')({
                         autoprefixer: false,
                         calc: false,
                         colormin: false,
                         convertValues: false,
                         core: false,
                         discardComments: { removeAll: true },
                         discardDuplicates: false,
                         discardEmpty: false,
                         discardOverridden: false,
                         discardUnused: false,
                         filterOptimiser: false,
                         filterPlugins: false,
                         funtionOptimiser: false,
                         mergeIdents: false,
                         mergeLongHand: false,
                         mergeRules: false,
                         minifyFontValues: false,
                         minifyGradients: false,
                         minifyParams: false,
                         minifySelectors: false,
                         normalizeCharset: false,
                         normalizeUnicode: false,
                         normalizeString: false,
                         normalizeUri: false,
                         reduceBackgroundRepeat: false,
                         orderedValues: false,
                         reduceDisplayValues: false,
                         reduceIdents: false,
                         reduceInitial: false,
                         reducePositions: false,
                         reduceTimingFunctions: false,
                         reduceTransforms: false,
                         svgo: false,
                         styleCache: false,
                         uniqueSelector: false,
                         zindex: false
                    })
               ]
          }
     }
},
```

