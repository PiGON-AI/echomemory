# Security

Found something security- or privacy-relevant? Please email
**milo@echotools.dev** (read by both partners) instead of opening a public
issue. We take the no-telemetry, everything-local promises seriously, and
reports that test them are welcome and will be answered.

What EchoMemory promises, so you know what to test:

- **No telemetry, no server, no account.** The only network code is the
  Ollama brain you choose, to the host you set.
- **Your notes stay yours.** They are plain files in `.milo/` in your
  project. The folder ignores itself in git, and no AI coding tool is
  connected to it.
- **Milo never writes a note on his own.** A note he condenses or summarizes
  for you waits in your Inbox until you approve it; that rule lives in the
  storage engine, not in a setting.
- **A project can't steer Milo.** Notes that arrive in someone else's copy
  of a project reach no AI brain until you have checked and trusted them,
  and a project's own settings can't change where your words go.
- **Milo's security check never prints a secret.** It reports where
  something secret-shaped appears (file and line), never the value.

The complete list of what EchoMemory reads, writes and hands on is
[DISCLOSURES.md](DISCLOSURES.md). If that page and the extension ever
disagree, that's a bug, and we'd like to hear about it.
