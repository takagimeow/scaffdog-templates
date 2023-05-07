---
name: "vscode-debug-expo"
root: ".vscode"
output: "**/*"
ignore: []
---

<!--
  次の拡張機能をインストールする
  - msjsdiag.vscode-react-native
  Expoアプリを開いたらControl + Command + zでデバッグメニューを開く
  - Start Remote Debuggingを選択する
  - 自動的に開くブラウザを閉じる
  VSCodeの設定を開き、次の設定を追加する
    - "react-native.packager.port": 19000
  デバッグに関してはこちらの記事を参照
  - https://qiita.com/pyuta/items/790735749c6f46566089
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
      "name": "Attach to packager",
      "request": "attach",
      "type": "reactnative",
      "cwd": "${workspaceFolder}/apps/expo-app",
      "preLaunchTask": "npm: start:clear",
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
      "script": "start:clear",
      "problemMatcher": [],
      "label": "npm: start:clear",
      "detail": "expo",
      "isBackground": true,
      "group": {
        "kind": "build",
        "isDefault": false
      },
      "options": {
        "cwd": "${workspaceFolder}/apps/expo-app"
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
