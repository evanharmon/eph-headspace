# Make Lodash available across app
`var _ = require('lodash');`

`new webpack.ProvidePlugin({ _: 'lodash' })`
