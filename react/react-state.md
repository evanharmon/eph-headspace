# REACT STATE

## Summary

Notes on using state with React and React Hooks

## Resources

[Medium Synthetic Events](https://medium.com/trabe/react-syntheticevent-reuse-889cd52981b6)

## Stateless function

```
import Header from "./header/app-header";
export default (props) => {
     return (
          <div className="container">
               <Header></Header>
               {props.children}
          </div>
     )
}
```

## Error Synthetic event reuse

## Nulls

Use nulls with arrays. null means api call hasn't returned yet
