# REDUX

## Object name in combineReducers matters!
### error in connect is a prop coming in as type function 'checkType'
`const reducer = combineReducers({ note, message, editor });`
```
export default connect(
  state => ({
    editorState: state.editor.editorState,
  }),
  {
    onSaveEditorState: fromNote.onSaveEditorState,
  }
)(EditorWindow);
```

## Use enableReinitialize=true passed to form components
without that, passing an empty object that would otherwise later be filled out
by some redux state will make that form always appear blank. was banging my
head trying to solve race conditions

## Guide for using React, Redux, ImmutableJS
(https://www.sitepoint.com/how-to-build-a-todo-app-using-react-redux-and-immutable-js/)

## Reducer returned undefined at initialization
(http://stackoverflow.com/questions/33749759/read-stores-initial-state-in-redux-reducer/33791942#33791942)
