# NINJA

## Summary

Notes on building with Ninja

## Resources

[Manual](https://ninja-build.org/manual.html)

## Ninja Build

#### Control Output / Parallel Jobs

only run one job at a time. Ninja defaults to running in parallel.

```bash
ninja -C build -j 1
```

#### Verbose Mode

```bash
ninja -v -C build
```

## Ninja Test

## Ninja Tools

All commands should be run from the directory containing the file `build.ninja`

#### Browse Dependency Graph

\*\* haven't gotten this to work yet

default port is `8000`

```bash
ninja -t browse --port=8000
```

disable opening web browser

```bash
ninja -t browse --port=8000 --no-browser mytarget
```

#### Targets

print list of targets

```bash
ninja -t targets
```

#### Commands

print list of commands in build

```bash
ninja -t commands
```

#### Compilation Database

```console
ninja -t compdb cxx > compile_commands.json
```
