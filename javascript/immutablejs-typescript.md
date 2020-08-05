# Map
```
map<M>(
mapper: (value?: T, key?: number, iter?: Iterable<number, T>) => M,
context?: any
): Iterable<number, M>
```
## Mapper Explanation
If a value, then text: `'add'`
If a key, then number: `0`
If an iterable, then Key and value

# findIndex()
```
findIndex(
predicate: (value?: T, index?: number, iter?: Iterable.Indexed<T>) => boolean,
context?: any
): number

// predicate (state) is an iterable
state.findIndex(i => {
     return i.get(id) === action.id;
}
```
