# REACT LIFECYCLE
## Mounting
### `componentWillMount()`
Triggers on both client and server, once before render()
Use to load data async and force render thru setState

### `componentDidMount()`
Triggers on client only
Access to DOM available. Remember to clean up on unmount

## Mounted
### `componentWillReceiveProps(nextProps)`
Trigger: prop change
use to modify component stated based on received props

### `shouldComponentUpdate({ nextProps }, { nextState })`
Trigger: state change
optimize rendering. `return false` to skip render

### `componentWillUpdate(nextProps, nextState)`
Cannot use setState()
set class properties

### `render()`

### `componentDidUpdate(nextProps, nextState)`
Trigger: state change
Use to modify DOM from another code to work with React

## Unmounting
### `componentWillUnmount()`
clean up, usually based on componentDidMount actions
