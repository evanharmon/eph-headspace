# AR

## Summary

Notes on using the `ar` archive utility for c/cpp

## View Object Files

```console
ar t libarchive.a
```

## Extract Object File

```console
ar x libarchive.a
```

## Turn Thin Archive Into Normal Archive

[SO](https://stackoverflow.com/questions/25554621/turn-thin-archive-into-normal-one)

```console
for lib in `find -name '*.a'`;
    do ar -t $lib | xargs ar rvs $lib.new && mv -v $lib.new $lib;
done
```
