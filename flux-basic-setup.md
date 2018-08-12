# FLUX - BASIC SETUP

## Folders / index start
actions/actions.js
components/app.js
constants/constants.js
dispatchers/dispatchers.js
stores/
index.js

## Basic Constants
List of Actions
```
export default {
  ADD_ITEM: 'ADD_ITEM',
  REMOVE_ITEM: 'REMOVE_ITEM',
  INCREASE_ITEM: 'INCREASE_ITEM',
  DECREASE_ITEM: 'DECREASE_ITEM'
}
```

## dispatchers.js Basic Dispatcher Wrapper
```
import {Dispatcher} from "flux";

const flux = new Dispatcher();
export function register(callback) {
  return flux.register(callback);
}
export function dispatch(actionType, action) {
  flux.dispatch(actionType, action);
}
```

## actions.js Basic Actions
```
import Constants from "../constants/constants";
import {dispatch, register} from "../dispatchers/dispatchers";

export default {
     addItem(item) {
          dispatch({
               actionType: Constants.ADD_ITEM, item
          })
     },
     removeItem(item) {
          dispatch({
               actionType: Constants.REMOVE_ITEM, item
          })
     },
     increaseItem(item) {
          dispatch({
               actionType: Constants.INCREASE_ITEM, item
          })
     },
     decreaseItem(item) {
          dispatch({
               actionType: Constants.DECREASE_ITEM, item
          })
     }
}
```

## app.js Basic App
```
import React from "react";
import Actions from "../actions/actions";

export default class App extends React.Component {
     render() {
          return (
               <h1 onClick={Actions.addItem.bind(null, 'this is the item')}>A Flux App</h1>
          )
     }
}
```
