# VIM EX MODE

## Summary

Notes on using vim execute mode

## Resources

### Copy

:t address

#### Copy Word Under Cursor

`<C-R><C-W>`

#### Copy Range of Lines (Relative Mode)

`:-10,-1t-11`

#### Copy command to system clipboard

Steps: bring up command history, j/k to select line, copy using system clipboard

```
q:
"+yy
```

#### Copy search to system clipboard

Steps: bring up search history, j/k to select line, copy using system clipboard

```
q/
"+yy
```

### Paste

#### Paste in command line

`<C-R>"`

### Move

`:m address, address`

#### Move Range of Lines (Relative Mode)

10 total lines in this example `:+22,+32m.`

### Delete

#### Delete Range of Lines

`:53,105d`

#### Delete Range of Lines (Relative Mode)

`:-20,-5d`

#### Norm delete all characters after certain line

ex: v.search.results.test = res.data;

`:%norm f=C`

### Add comma at end

`:'<,'>norm A,`

### Repeat macro over range of lines

`:5,10norm! @q`

### Execute command from shell

`:!cmd`

### Send File to Shell as Commands

`:write !sh`

### Sort Part of a CSV file

`:2,$!sort -t',' -k2`

### Execute command and insert stdout at cursor

`:read !ls ./rules`

### Replace space indents with tabs

`:retab`

### Replace tabs indents with spaces

if no tabstop set or its set to expandtab then replace tabs with spaces

`:retab`

### Get Count of search

`%s/TestPhrase//gn`

### Break Line In To Multiple Lines

example: csv list to multiple lines without comma

```
:s/,/\r/g
```

### Join Multiples In To Single Line

example:

```
:%j
```

## Sort Comma Delimited Line

```
:call setline(line('.'),join(sort(split(getline('.'), ',\s*')), ','))
```
