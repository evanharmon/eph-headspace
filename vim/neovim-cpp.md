# NEOVIM CPP

## Summary

Setting up Neovim for cpp development

## Resources

- [Modern CPP in Neovim](https://chmanie.com/post/2020/07/17/modern-c-development-in-neovim/)
- [CCLS Github](https://github.com/MaskRay/ccls/wiki/Build)

## Install CCLS

don't use brew to install CCLS, often outdated

```console
brew install llvm # install llvm first
// check version and set as env var
brew info llvm
export LLVM_VERSION=11.0.0

git clone --depth=1 --recursive https://github.com/MaskRay/ccls
cd ccls
cmake -H. -BRelease \
  -DCMAKE_BUILD_TYPE=Release \
  -DCMAKE_PREFIX_PATH=/usr/local/Cellar/llvm/$LLVM_VERSION/lib/cmake \
  -DCMAKE_C_COMPILER=/usr/bin/clang \
  -DSYSTEM_CLANG=ON
  -DC_MAKE_CXX_COMPILER=/usr/bin/clang++ \

cmake --build Release
cmake --build Release --target install
```
