This folder contains the VS Code Dev Container configuration for the Desserter project.

How to open in VS Code

1. Install the "Dev Containers" (Remote - Containers) extension in VS Code.
2. In the command palette choose: "Dev Containers: Reopen in Container".
3. The container image uses Node 20 and includes Java 17 (for optional `npx expo prebuild`).

Included files

- `devcontainer.json` — main configuration (uses the official Node 20 devcontainer image).

Ports forwarded

- `3000` — Docusaurus docs (run `npm run docs`).
- `8081` — Expo Metro (run `npm start`).
- `19002` — Expo DevTools.

Post-create actions

The container runs a post-create command to install dependencies in the repo root and the `website/` folder:

```
npm ci
npm --prefix website ci
```

Notes

- iOS simulator still requires macOS/Xcode and is not available inside the container.
- For Android emulator performance, prefer running the emulator on the host and connect the container to it.

If you want me to also add an optional Dockerfile, Android toolchain, or push these changes to the remote, tell me and I'll proceed.
