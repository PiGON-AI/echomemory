# Third-Party Notices

EchoMemory bundles **no third-party code at runtime**. The extension and its
uninstall script are built from in-house packages
(`@echotools/echomemory-core`, `@echotools/echomemory-retrieval`,
`@echotools/echomemory-correctness` and `@echotools/core`), which depend only
on each other and on Node.js built-ins.

Tooling used to build the package (TypeScript, esbuild, and `@vscode/vsce`)
is not shipped inside it.

The VS Code extension API is used under Microsoft's terms for extension
authors. When you choose Ollama for Milo's brain, EchoMemory talks to your
own Ollama over its HTTP API; no Ollama code ships inside this package.
Claude Code, Codex, Gemini, Antigravity, Kimi Code, Copilot and Ollama are
trademarks of their respective owners; names are used only to state
compatibility.

If a future release adds third-party code or media, its license text will be
reproduced or linked here as that license requires.
