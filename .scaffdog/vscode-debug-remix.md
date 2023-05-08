---
name: 'vscode-debug-remix'
root: '.vscode'
output: '**/*'
ignore: []
---

<!--
remix.config.jsにて、`sourcemap: true`を設定
詳細については、こちらを参照
https://gist.github.com/kiliman/a9d7c874af03369a1d105a92560d89e9
-->

# `launch.json`

```json
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "command": "npm run dev",
      "name": "Run npm run dev",
      "request": "launch",
      "type": "node-terminal",
      "cwd": "${workspaceFolder}"
    },
    {
      "name": "Attach by Process ID",
      "processId": "${command:PickProcess}",
      "request": "attach",
      "skipFiles": ["<node_internals>/**"],
      "type": "pwa-node"
    }
  ]
}
```