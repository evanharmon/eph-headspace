# HUSKY

[Github](https://github.com/typicode/husky)

## Summary

Notes on using git hooks package Husky

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
