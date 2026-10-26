# What Milo does

Plain-language reference for EchoMemory. Written for someone who is **new
to coding with AI**, not for an engineer, because that is most of the
people who will use this.

Rule for this file: **only what actually works goes in the "today"
section.** If it is not built, it lives under "what we're building". No
promises in the present tense.

> Both lists are timestamped. When we build something, we move it up and
> re-date it, so we never lose track of what is real.

---

## What Milo does today

**As of 2026-10-26 · EchoMemory 1.0.1 (preview)**

### The problem he solves

You decide things while you code: how the project deploys, why a hard bug
happened, what to try next time. A week later, it's gone, and you work it
out again.

Milo remembers instead.

### Where your notes live

In **your project folder**, in a folder called `.milo/`. Plain text files
you can open and read. Nothing is uploaded anywhere, and the folder keeps
itself out of git, so nothing in it is committed.

Two things matter in there:

- **`notes.md`**: all your notes for this project, newest first, on one
  readable page.
- **`entries/`**: the actual notes, one small file per note.

`notes.md` is written *for* you, not *by* you: Milo prints it from the
notes. If you want to change a note, use the menu or ask Milo; editing the
page changes nothing he remembers.

### Saving something

1. **Pin & Note**: from Milo's menu on the bottom bar. You type the note, it
   saves.
2. **By voice or in his bar**: tell Milo "pin this, ...". A card asks your
   yes.
3. **Ask Milo to write it for you**: "remember what I just said" and he
   condenses it into one clear note; "summarize my note about deploys" and he
   sums it up. Either way, his version **waits in your Inbox** for your OK.

### Asking what you know

- **Ask Milo** (`Ctrl+Alt+M`, `Cmd+Alt+M` on Mac): type a question, get the
  exact notes back with where each one came from and when. **He looks it up
  himself: no AI involved.** That means it's instant, it works offline, and
  it costs you nothing. He matches words, so a note has to say "code review"
  for a question about code review to find it.
- **Out loud or in his bar**: hold the button in Milo's window, or type, and
  ask. He answers in his voice, from your notes.
- **Milo's summary**: "what did we do yesterday", "the last hour", or "since
  your last summary". The list of what happened in your notes, saved, and its
  headline spoken.
- **Milo's updates**: a glance in the Explorer at the last things that
  happened in your notes.

### The Inbox: why you approve things

- **When *you* write a note, it's saved. Done.** No approval, it's your own
  words.
- **When *Milo* writes one for you**, a note he condensed, a summary of one
  of your notes, or his security report, it **waits for you** in your Inbox. You **Approve** it,
  **Edit** it and approve, or **Forget** it.

That waiting is not a setting someone can flip by accident: it's built into
how saving works. The reason is simple: an AI should not be able to quietly
decide what you remember.

### Milo knows your tools

Ask Milo about slash commands and skills in **Claude Code, Codex and Kimi
Code**: what a command does, how to rename a session, what a skill is. He
answers from a checked guide that ships with EchoMemory, never from a guess.
Ask for help with EchoVoice or EchoAvatar and he answers from his support
guide, and offers Milo's office (inside VS Code) for anything deeper.

### Checks

- **Milo's security check**: on request, a quick first pass over the files
  git tracks (secrets committed by mistake, a missing `.gitignore` line, a
  security policy, risky GitHub Actions settings). No AI, nothing sent
  anywhere. The report waits in your Inbox. It never says your project is
  safe; it says what it checked.
- **Your usage**: ask "how much do I have left?" and Milo gives Codex's
  limits and opens Claude Code's own usage panel. Optionally, a heads-up
  before your Claude Code session runs out.

### Privacy, concretely

- Nothing leaves your machine through Milo. There is no account and no
  server.
- **Milo's brain is the one exception.** When you talk to Milo, what you
  say, and any notes he reads to answer you, go to the brain you chose: your
  own Copilot, or your own Ollama (on your machine, or hosted with your key).
  **Ask Milo** never uses a brain.
- **No AI coding tool is connected to your notes.** EchoMemory writes nothing
  into your tools' instruction files. The one setting it can add is the
  optional session-limit step for Claude Code, on your yes.
- **Notes from someone else's copy stay put** until you've checked and
  trusted them.
- Nothing goes into git: the `.milo/` folder ignores itself.
- Uninstalling Milo **never deletes your notes.**

### The bottom bar

Bottom-right of VS Code, next to EchoAvatar: **EchoMemory**, and how many
things are waiting for you. Click it for the menu with every door.

### What Milo can NOT do today

Being straight about this so nobody promises it by mistake:

- **Milo can't read or change your code**, run your project's commands,
  browse the web, send messages or use a calendar. (His security check runs
  git to list your files, and he can open a terminal or a coding tool when
  you ask.) For code help, ask your AI coding tool.
- **Milo does not use AI to answer Ask Milo.** That's deliberate. It's what
  makes him instant and free.
- **Same machine only.** WSL, Remote-SSH, Dev Containers and Codespaces
  aren't supported in this release.

---

## What we're building next

**Planned as of 2026-10-09.**

### 1. Milo shows you around

Today the walkthrough lives in VS Code's Welcome page. Next, Milo walks you
through EchoMemory himself.

### 2. More words for Milo

"Where were we" in the morning, and the Inbox by voice.

### 3. An EchoTools front door

One listing that installs the suite in a click, for people who come from
the website rather than a store page.

### 4. Searching your AI tools' docs

Ask Milo how something works in Claude Code, Codex or Kimi Code, and he
searches their published docs for you, with a link to the page.

---

## Later: real possibilities, not commitments

- **Reminders and notifications**, and **adding things to your calendar**:
  the team is exploring these.

- **Summaries of your AI tools' instruction files**: "what changed in our
  CLAUDE.md since last week?"
- **Search by meaning instead of words** (using a model running on your own
  machine, so it stays private and free): ask "that caching thing" and find
  the note that never used the word "caching".

---

## The words we use

Because half of understanding a tool is its vocabulary. These are the only
words we say to people:

| We say | We never say |
|---|---|
| **Pin & Note** | "remember a note", "commit a memory" |
| **your Inbox** | "pending", "quarantine", "approval queue" |
| **Approve** / **Forget** | "transition", "approval state" |
| **Ask Milo** | "query the corpus", "retrieval" |
| **your AI tools** | "CLIs", "agents", "MCP clients" |
| **waiting for your OK** | "quarantined pending approval" |

The engineering words still exist inside the code, where they belong. They
just never reach a screen, and there's an automatic check that fails the
build if one slips through.
