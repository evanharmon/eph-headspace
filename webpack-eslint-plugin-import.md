# Config is in your .eslintrc .eslint.json file
```
---
extends:
  - eslint:recommended
  - plugin:import/errors
  - plugin:import/warnings
```

# or configure manually:
```
plugins:
  - import
rules:
  import/no-unresolved: [2, {commonjs: true, amd: true}]
  import/named: 2
  import/namespace: 2
  import/default: 2
  import/export: 2
```

