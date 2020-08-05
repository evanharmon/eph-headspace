# MAC OS X

## Summary

General notes on working with MAC OS X

### FINDER

#### Show Hidden Files in Finder

- Open Terminal found in Finder > Applications > Utilities
- In Terminal, paste the following:
  `defaults write com.apple.finder AppleShowAllFiles YES`
- Hold the 'Option/alt' key, then right click on the Finder icon in the dock
  and click Relaunch

#### Delete Finder Plist

can help with slowdowns / crashing of finder

```console
rm ~/Library/Preferences/com.apple.finder.plist
```

### Preview

#### Clear Cache To Fix Crashing

- [Clear Preview Cache](https://becomethesolution.com/blogs/mac/mac-clear-preview-cache)

```console
defaults delete com.apple.Preview.LSSharedFileList RecentDocuments
defaults write com.apple.Preview NSRecentDocumentsLimit 0
defaults write com.apple.Preview.LSSharedFileList RecentDocuments -dict-add MaxAmount 0
killall Dock
```
