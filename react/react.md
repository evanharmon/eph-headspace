# REACT GENERAL

## Summary

General notes on using reactjs

## Resources

- [React Snippets 30 seconds of code](https://www.30secondsofcode.org/react/p/1/)
- [Synthetic Events](https://reactjs.org/docs/events.html)

## use font-awesome

only yarn install and CSS import required
`import 'font-awesome/css/font-awesome.css'`

## Virtual DOM Performance

(https://www.bimeanalytics.com/engineering-blog/you-put-your-react-into-my-angular/)
React manages DOM in-memory
Computes the minimal set of mutations to do on the real DOM and does them in Batch

## Comments have to be wrapped in curly braces using block comments

{/_ This is a comment _/}

## Destructure this.props in render

```
render() {
     const { user } = this.props;
     return ();
}
```

## Destructure props in component

```
const Btn = ({
     name,
     onClick
}) => {
// same as using this.name and this.onClick here
};
```

## Show booleans in JSX html

`{completed.toString()}`

## React DOM

React DOM is for including React in the page before React DOM

## Inline styling

`<div style={{ display: 'inline-block' }}></div>`

## Styling with object

```
const divStyle = { color: 'white', textAlign: 'center' };
<div style={divStyle}></div>
```

## &nbsp non breaking spaces

use unicode
`<div>{"\u00a0"}</div>`
