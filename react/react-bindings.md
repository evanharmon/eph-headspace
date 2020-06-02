# REACT BINDINGS

## Bind function
```
class App extends Component {
  constructor(props) {
    super(props);
    this.onHandlerChange.bind(this)
  }
  onHandlerChange() {
    console.log('on handler change');
  }
  render() {
    <div>
      <input type="button" onClick={ () => { this.onHandlerChange() } />
    </div>
  }
}
```
