# REACT-ROUTER

## Summary

Notes on using react router

## Resources

[Docs](https://reacttraining.com/react-router/web/guides/quick-start)
[History Docs](https://github.com/ReactTraining/history/blob/master/docs/GettingStarted.md)
[RWeiruch UnMounted Component Set State Warning](https://www.robinwieruch.de/react-warning-cant-call-setstate-on-an-unmounted-component/)
[React Hooks And Context Router](https://medium.com/trabe/implementing-private-routes-with-react-router-and-hooks-ed38d0cf93d5)
[React Router Amplify Auth](https://www.rockyourcode.com/custom-react-hook-use-aws-amplify-auth/)
[GH Testing](https://github.com/ReactTraining/react-router/blob/master/packages/react-router/docs/guides/testing.md)

## Index Route

- doesn't take a path - just a component
- default component to show when path matches that of our parent route path

## Link

- Renders as an <a> anchor element
- css classes can be passed to Link

```javascript
<Link to="/cart" className="btn btn-success">
  Cart
</Link>
```

## Navigate programatically

use `<Redirect />` in combination with `setState()`

```javascript
class Login extends React.Component {
  state = {
    redirectToReferrer: false,
  }

  login = () => {
    fakeAuth.authenticate(() => {
      this.setState({ redirectToReferrer: true })
    })
  }

  render() {
    const { redirectToReferrer } = this.state

    // here is the important part
    if (redirectToReferrer) {
      return <Redirect to="/" />
    }
    //

    return (
      <div>
        <p>You must log in to view the page at {from.pathname}</p>
        <button onClick={this.login}>Log in</button>
      </div>
    )
  }
}
```

## Authenticated Routes

[Docs Example](https://reacttraining.com/react-router/web/example/auth-workflow)

## Auth Api Call PrivateRoute

[SO](https://stackoverflow.com/questions/49309071/react-private-router-with-async-fetch-request)

## Pass Router Information Through Custom Component

```javascript
const MyRouteComponent = ({ ...options }) => (
  <>
    <MyComponent {...options} />
  </>
)
```

## Simple Example

```javascript
ReactDOM.render(
  <Router>
    <div>
      <Route exact path="/">
        <Home />
      </Route>
      <Route path="/news">
        <NewsFeed />
      </Route>
    </div>
  </Router>,
  node
)
```

## Hooks

### Test React-Router Hooks With Jest

```javascript
test('renders without failing', () => {
  jest.mock('react-router-dom', () => ({
    ...jest.requireActual('react-router-dom'),
    useParams: () => ({
      id: '123',
    }),
    useRouteMatch: () => ({ url: '/records/123' }),
  }))
  const renderer = new ShallowRenderer()
  renderer.render(
    <MemoryRouter>
      <Records />
    </MemoryRouter>
  )
  const result = renderer.getRenderOutput()
  expect(result).toBeTruthy()
})
```

## Common Mistakes

### Redirects Aren't Working Outside Switch

make sure you don't have MULTIPLE <BrowserRouter>'s. Example, one in
'src/index.js' and yet another in 'src/routes.js'

## Debugging

[SO Debug Example](https://stackoverflow.com/questions/34093913/how-to-debug-react-router)

```javascript
class DebugRouter extends Router {
  constructor(props) {
    super(props)
    console.log('initial history is: ', JSON.stringify(this.history, null, 2))
    this.history.listen((location, action) => {
      console.log(
        `The current URL is ${location.pathname}${location.search}${location.hash}`
      )
      console.log(
        `The last navigation action was ${action}`,
        JSON.stringify(this.history, null, 2)
      )
    })
  }
}

class App extends Component {
  render() {
    return (
      <DebugRouter>
        <Switch>
          <Route exact path="/login" name="Login Page" component={Login} />
          <Route path="/" name="Home" component={DefaultComponent} />
        </Switch>
      </DebugRouter>
    )
  }
}
```

## Listen To History Changes

```javascript
useEffect(() => {
  const unlisten = history.listen((location, action) => {
    // location is an object like window.location
    console.log(action, location.pathname, location.state)
  })
  return () => unlisten()
})
```
