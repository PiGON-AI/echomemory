# Third-Party Notices

EchoMemory bundles **no third-party code at runtime**. The extension, its
uninstall script, and the MCP server it installs are built from five
in-house packages (`@echotools/echomemory-core`, `-mcp`, `-adapters`,
`-retrieval`, `-correctness`), each of which depends only on the others and
on Node.js built-ins. The MCP server speaks the protocol directly over
standard input and output; it does not embed an SDK.

Tooling used to build the package (TypeScript, esbuild, and
`@vscode/vsce`) is not shipped inside it.

The VS Code extension API is used under Microsoft's terms for extension
authors. Claude Code, Codex, Gemini, Kimi Code, and Copilot are trademarks
of their respective owners; names are used only to state compatibility. The
background carrier launches the tool's own installed binary (`claude`,
`codex`, `gemini`) with the arguments shown on its consent card; none of
those programs ship inside this package.

If a future release adds third-party code or media, its license text will be
reproduced or linked here as that license requires.
