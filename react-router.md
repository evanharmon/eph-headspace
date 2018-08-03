# REACT-ROUTER

## Index Route
- doesn't take a path - just a component
- default component to show when path matches that of our parent route path

## Link
- Renders as an <a> anchor element
- css classes can be passed to Link
`<Link to="/cart" className="btn btn-success">Cart</Link>`

## Navigate programatically
use `<Redirect />` in combination with `setState()`
```
class Login extends React.Component {
  state = {
    redirectToReferrer: false
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
      return (
        <Redirect to="/"/>
      )
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
