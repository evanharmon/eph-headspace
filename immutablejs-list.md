# Find value of a Map in a List
`list.getIn('id', 0);`

# Get size of List
`list.size`

# Get index'd part of list and convert to JS
`list.get(1).toJS()`

# Create Native List from Maps
```
const list = Immutable.List.of(
     Immutable.Map({id: 0}),
     Immutable.Map({id: 1})
)
```

# find and update by Id in a List
```
const idx = state.findIndex(item => item.get('id') === 2);
return state.update(idx, item => return item.set('completed', completed));
```


# Iterate through List via Map to update Value
```
return state.map(i => {
     if (action.data.id === i.get('id')) {
          return i.update('completed', completed => !completed);
     } else {
          return i;
     }
}
```

# Console log key value pairs of maps inside a List
`newState.map(i => console.log(JSON.stringify(i.toObject())));`
