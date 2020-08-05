# PRETTIER

## Summary

Notes on using prettier

## Resources

- [Docs](https://prettier.io/docs/en/ignore.html)
- [RWieruch Using Prettier in Vscode](https://www.robinwieruch.de/how-to-use-prettier-vscode)

## CLI

### Format Markdown To 80 Char Max

```
prettier --prose-wrap="always" README.md
```

### Write Prettier Changes To File

This command is destructive!

```
prettier --prose-wrap="always" --write README.md
```

## Code

### Ignore Javascript Code

```
// prettier-ignore
```

### Ignore JSX Code

```jsx
{/* prettier-ignore */}
```

### Ignore Sections Of Code

use a `.prettierignore` file instead with globs
