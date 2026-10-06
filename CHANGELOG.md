# Changelog

## 1.0.0 (preview)

*Why this release: it's the first. EchoMemory gives your AI coding partners
a shared memory that lives in your project as readable text, and it's marked
preview because this is our first ship of it.*

- **Memory in your repository**: one small file per note in
  `.echomemory/entries/`, and a readable `team.md` that Milo rebuilds from
  them, so five tools can write at once and never scramble each other.
- **your Inbox**: when *you* save a note it's saved; when an *AI tool*
  saves one it waits for your Approve or Forget. Built into how saving works,
  not a setting a tool can flip.
- **EchoMemory on the bottom bar**, next to EchoAvatar: it says when notes
  are waiting for you, and one click opens the menu with every door.
- **Milo's updates** in the Explorer: a glance at the last things that
  happened in this project's memory, newest first. Who saved what through
  which tool, what you approved, which brief went where, what you asked Milo
  for. Each line quotes the note it is about; a click opens Milo's Memory.
- **Ask Milo** (`Ctrl+Alt+M`): type a question, get the exact notes back with
  where each came from and when. No AI involved: instant, offline, free.
- **Connected to Claude Code, Codex, Kimi Code, Gemini, and Antigravity** in
  one step, with a preview of every file before it's touched, a backup first,
  and an undo.
- **Notes between your tools**: a note that starts `[Brief → Codex]` (or
  any tool) is an ordinary note in your Inbox; a connected tool reads it
  through the memory tools and answers with a `[Report → you]` note.
- **Milo talks back** (with EchoAvatar 1.1.0 and EchoVoice 1.1.0): hold the
  button and talk. A question is answered from memory in Milo's voice, quotes
  only. On your own Copilot, Milo can also open his doors for you: reads and
  his own body run on your word; anything that writes memory comes back as a
  proposal and runs only on your yes. Memory quotes are verbatim and marked;
  the sentences around them are Copilot's.
- **Milo knows his way around**: ask him how EchoMemory works (team.md
  and user.md, the Inbox, briefs between tools, receipts) or for help with
  EchoVoice and EchoAvatar, and he answers from a guide that ships inside
  the extension, written from EchoMemory's own docs and echotools.dev. For
  anything deeper he offers Milo's office, which opens right here in VS Code.
- **A security first pass**: ask Milo to check your repository's security
  (or pick *Milo's security check* from the menu). Quick local checks, no AI
  and nothing sent anywhere: committed secret files and secret-shaped text
  (reported by file and line, never the value), `.env` in `.gitignore`, a
  lockfile, a security policy, risky GitHub Actions settings. The result is
  a brief in your Inbox: proof it, approve it, and your partners do the deep
  dive (their own review, your database rules, error monitoring,
  dependencies, an adversarial pass) and report back. It never says "safe".
- **How much do I have left?**: Milo reads Codex's limits from its own
  session files and opens Claude Code's panel, where Account and Usage shows
  the live numbers. With EchoAvatar 1.1.0, the three- and five-hour break
  check-ins carry the Codex line and a *Check Claude usage* button. For
  Claude Code in a terminal, an optional status line step gives a heads-up
  at 85%, 90% and 95% of your five-hour window.
- **Links stay in VS Code**: the team's links (tech support, reporting a
  problem, a review) open in VS Code's own browser tab. When you ask for
  something Milo can't do yet, he offers once to draft an email to
  milo@echotools.dev.
- **Milo inside Copilot**: `@milo` in chat, and two agent-mode tools:
  Copilot can ask what the team decided, and hand Milo a note that waits in
  your Inbox like any other.
- **Signposts, not notes**: small marked blocks in `CLAUDE.md`, `AGENTS.md`,
  and `GEMINI.md` (only if you say yes) that tell your tools where memory
  lives. Plus `/remember`, `/digest` and `/diet` as skills for Claude Code,
  Codex and Kimi Code, each one ending with "the note waits in your Inbox".
- **Remember by default**: the skills tell your tool to record a decision in
  the same breath as the commit, and a commit whose message has a
  `Decision:`, `Ruling:` or `Lesson:` line proposes that line in your Inbox,
  quoting the commit. Off with one setting.
- **Milo's brain, yours**: Copilot in VS Code; in editors without Copilot
  (the Antigravity IDE, Cursor, Windsurf) your own Ollama, a model on your
  machine or Ollama's hosted API with your key. Choose Milo's brain model
  shows size and where each model runs; the key lives in the secret store.
- **Private by construction**: no telemetry, no server. The only network code
  is the Ollama brain you choose, to the host you set. Nothing goes into git
  until you turn one of three switches on, each with a preview. Your session
  digests, your notes about yourself, and any note you mark **Keep this from
  the tools** are never given to an AI, and a kept note stays out of
  `team.md`. Memory that arrives from someone else's clone stays inert until
  you've read it.
- **The suite**: EchoMemory is Milo's memory and installs with Milo himself
  (EchoAvatar, about 48 MB) and his voice (EchoVoice), because the three are
  one companion.
- **Uninstalling never deletes your memory.**

Changes from here on are listed per release, in plain language.
