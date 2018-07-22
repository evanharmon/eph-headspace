# IMMUTABLEJS
http://facebook.github.io/immutable-js/

# Use fromJS to create maps or lists
too much work to try and create native maps or lists

[Example of Redux and ImmutableJS](https://www.sitepoint.com/how-to-build-a-todo-app-using-react-redux-and-immutable-js/)

# Test equality
`Immutable.is(imm1, imm2);`

# Working with JS objects in a Map and List
```
import { Map as iMap, List as iList } from 'immutable';
const Hands = (state = iList(), action) => {
     switch (action.type) {
          case 'ADD_HAND':
               return state.push(iMap(action.data));
     }
};
const stateBefore = iList().push(iMap({ id: 0 }));
const action = { type: 'ADD_HAND', data: { id: 1 } };
Hands(stateBefore, action);
```

# Use in React
## Render list of maps
```
<ul>
     {this.props.hands.map(i => (
          <li key={i.get('id')}>{i.get('id')}</li>
     ))}
</ul>
```

# MAPS
Get key/values in a Map
`const ary = action.filter((val, key) => key !== 'type');`
