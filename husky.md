# HUSKY

## Summary

Notes on using git hooks package Husky

## Resources

[Github](https://github.com/typicode/husky)
[Taming Husky With Scripts](https://medium.com/trabe/taming-the-husky-db15632c106f)
[Git Hooks](https://git-scm.com/docs/githooks)

## Install

```console
npm install husky --save-dev
```

## Setup

in package.json

```json
{
  "husky": {
    "hooks": {
      "pre-commit": "npm test",
      "pre-push": "npm test",
      "...": "..."
    }
  }
}
```

## Example Script To Limit Husky

```json
{
  "husky": {
    "hooks": {
      "pre-commit": "scripts/skip-husky.sh || npm run precommit"
    }
  }
}
```

```bash
#!/bin/bash

# Only run husky on src directory
[[ "$(git diff --staged --stat ./src)" == "" ]] && exit 0

exit 1
```
