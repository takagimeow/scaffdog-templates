---
name: "vscode-devcontainer"
root: ".devcontainer"
output: "**/*"
ignore: []
---

# `devcontainer.json`

```json
// For format details, see https://aka.ms/devcontainer.json. For config options, see the
// README at: https://github.com/devcontainers/templates/tree/main/src/typescript-node
{
  "name": "Node.js & TypeScript",
  // Or use a Dockerfile or Docker Compose file. More info: https://containers.dev/guide/dockerfile
  "image": "mcr.microsoft.com/devcontainers/typescript-node:0-16-bullseye",

  "customizations": {
    "vscode": {
      "extensions": [
        // GitHub Copilot
        "github.copilot",
        "github.copilot-labs",
        // Git
        "waderyan.gitblame",
        "donjayamanne.githistory",
        "eamodio.gitlens",
        "mhutchie.git-graph",
        // Prisma
        "prisma.prisma",
        "prisma.prisma-insider",
        // Linter
        "esbenp.prettier-vscode",
        // Prettier
        "esbenp.prettier-vscode",
        // TailwindCSS
        "bradlc.vscode-tailwindcss",
        // Snippet
        "vscode-snippet.snippet",
        // scaffdog
        "scaffdog.scaffdog-vscode"
      ]
    }
  }
  // Features to add to the dev container. More info: https://containers.dev/features.
  // "features": {},

  // Use 'forwardPorts' to make a list of ports inside the container available locally.
  // "forwardPorts": [],

  // Use 'postCreateCommand' to run commands after the container is created.
  // "postCreateCommand": "yarn install",

  // Configure tool-specific properties.
  // "customizations": {},

  // Uncomment to connect as root instead. More info: https://aka.ms/dev-containers-non-root.
  // "remoteUser": "root"
}
```
