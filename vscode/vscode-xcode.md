# VSCODE XCODE

## Summary

Notes on working with xcode projects in VSCODE

## Resources

- [SWLH Medium Blog](https://medium.com/swlh/ios-development-on-vscode-27be37293fe1)

## Setup

### Enable Swift Language Support

```console
xcrun sourcekit-lsp
```

`CTRL + C` to quit

### Build SourceKit-LSP Extension

```console
cd ~/.cache
git clone https://github.com/apple/sourcekit-lsp.git
cd sourcekit-lsp/Editors/vscode/
npm run createDevPackage
code --install-extension out/sourcekit-lsp-vscode-dev.vsix
```
