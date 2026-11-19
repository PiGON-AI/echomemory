# Security

Found something security- or privacy-relevant? Please email
**milo@echotools.dev** (read by both partners) instead of opening a public
issue. We take the no-telemetry, everything-local promises seriously, and
reports that test them are welcome and will be answered.

What EchoMemory promises, so you know what to test:

- **No telemetry, no server, no account.** The only network code is the
  brain you choose: the Ollama brain, to the host you set (or ollama.com
  with your key), or the Claude brain, to Anthropic's API with your own key.
  A guard fails the package if network code appears anywhere else.
- **Reminders, the calendar and contacts are kept on your machine.** When
  you ask Milo about your days, the reminders and meetings he reads go to the
  brain you chose, like your notes; contacts never do. EchoLive reads them
  through EchoMemory inside your editor; notes it files arrive in your Inbox
  as proposals.
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
