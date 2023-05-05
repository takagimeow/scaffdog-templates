---
name: "vscode-debug"
root: ".vscode"
output: "**/*"
ignore: []
---

# `launch.json`

```json
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "chrome",
      "request": "launch",
      "name": "Launch Chrome against localhost",
      "url": "http://127.0.0.1:5173/",
      "webRoot": ".",
      "preLaunchTask": "${defaultBuildTask}",
      "postDebugTask": "Terminate All Tasks"
    }
  ]
}
```

# `tasks.json`

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "type": "npm",
      "script": "dev",
      "problemMatcher": [],
      "label": "npm: dev",
      "detail": "vite",
      "isBackground": true,
      "group": {
        "kind": "build",
        "isDefault": true
      }
    },
    {
      "label": "Terminate All Tasks",
      "command": "echo ${input:terminate}",
      "type": "shell",
      "problemMatcher": []
    }
  ],
  "inputs": [
    {
      "id": "terminate",
      "type": "command",
      "command": "workbench.action.tasks.terminate",
      "args": "terminateAll"
    }
  ]
}
```
