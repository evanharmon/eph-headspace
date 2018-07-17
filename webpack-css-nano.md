# stop minification
## had to set all defaults to false...
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
