# VSCODE TASKS

## Summary

Notes on creating and running vscode tasks

## Resources

- [Task Docs](https://code.visualstudio.com/docs/editor/tasks#vscode)
- [Docker Tasks](https://code.visualstudio.com/docs/containers/reference)

## Custom Tasks

### Shell Script

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Run tests",
      "type": "shell",
      "command": "./scripts/test.sh",
      "presentation": {
        "reveal": "always",
        "panel": "new"
      }
    }
  ]
}
```
