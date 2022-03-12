# REACT REFS
Requires stateful component

## Summary
Notes on the use of refs in React

## Resources
- [React Doc](https://reactjs.org/docs/refs-and-the-dom.html)

## Get DOM Node of component
```
class Hand extends React.Component {
     componentDidMount() {
          const canvas = this.refs.canvas;
     }
     render() {
          return (
               <canvas ref="canvas"></canvas>
     }
}
```

## Provide input node value inside component
using immutablejs / redux in this example
```
class ItemApp extends React.Component {
     render() {
          <div>
               <input ref={node => this.input = node} />
               <button onClick={() => {
                    store.dispatch({
                         type: 'ADD_ITEM',
                         data: {
                              name: this.input.value,
                              id: 5
                         }
                    })
               }}>Add Item</button>
               <ul>
                    {this.props.items.map(i =>
                         <li key={i.get('id')}>{i.get('name')}
                         </li>
               </ul>
          </div>
     }
}
```
