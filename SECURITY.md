# Security

Found something security- or privacy-relevant? Please email
**milo@echotools.dev** (read by both partners) instead of opening a public
issue. We take the no-telemetry, everything-local promises seriously, and
reports that test them are welcome and will be answered.

What EchoMemory promises, so you know what to test:

- **No telemetry, no server, no account.** The only network code is the
  Ollama brain you choose, to the host you set.
- **A model never writes team truth on its own.** Every note an AI tool
  saves waits in your Inbox until you approve it; that rule lives in the
  engine, not in a setting a tool can flip.
- **Nothing goes into git** until you turn one of three switches on, each
  with a preview.
- **Notes you keep from the tools stay kept**: your session digests, your
  notes about yourself, and any note marked *Keep this from the tools* are
  never given to an AI.
- **Milo's security check never prints a secret.** It reports where
  something secret-shaped appears (file and line), never the value.

The complete list of what EchoMemory reads, writes and runs is
[DISCLOSURES.md](DISCLOSURES.md). If that page and the extension ever
disagree, that's a bug, and we'd like to hear about it.
