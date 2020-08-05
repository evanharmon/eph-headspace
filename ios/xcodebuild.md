# XCODEBUILD

## Summary

Notes on using the cli tool `xcodebuild` to build iOS / Mac apps

## Resources

## Build Project With All Targets

```console
xcodebuild -project MyProject.xcodeproj -alltargets -configuration Release
```

## Build Workspace With Scheme

```console
xcodebuild -workspace your_project.xcworkspace -scheme your_sheme
```
