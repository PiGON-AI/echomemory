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

**As of 2026-10-06 · EchoMemory 1.0.0 (preview)**

### The problem he solves

You work with an AI coding partner. It helps, you decide things together,
you fix a hard bug at 2am. Next session, it remembers none of it. Neither
does the *other* AI tool you use. So you explain everything again, and
again, and you pay for those explanations every time.

Milo remembers instead.

### Where the memory lives

In **your project folder**, in a folder called `.echomemory/`. Plain text
files you can open and read. Nothing is uploaded anywhere. Nothing is
shared with your team unless you switch that on yourself.

Three things matter in there:

- **`team.md`**: the shared notes for this project, a headline and a why
  per note. Any AI tool working on this project reads it first.
- **`entries/`**: the actual notes, one small file per note. This is why
  five different AI tools can add notes at the same time and never
  scramble each other's work: nobody edits one shared file.
- **`user.md`**: notes about *you* for this project, and a map of what
  lives where. Milo asks what to call you, once.

`team.md` is written *for* you, not *by* you: Milo rebuilds it from the
notes. If you want to change a note, change the note, not the summary.

### Saving something

Five ways, all the same result:

1. **Pin & Note**: from Milo's menu on the bottom bar. You type the note,
   say who may read it (everyone, or **keep this from the tools**), it saves.
2. **By voice**: hold the button in Milo's window and say "pin this, ...".
   A card asks your yes.
3. **Ask your AI tool to do it**: Claude Code, Codex, Gemini, Kimi, or
   Copilot can save a note for you, because Milo is connected to them. It
   waits for your OK.
4. **The `remember` skill** inside Claude Code, Codex or Kimi Code, if you
   let Milo install it.
5. **A line in a commit message.** Start a line with `Decision:`, `Ruling:`
   or `Lesson:` and Milo proposes it in your Inbox, quoting the commit. You
   can turn this off.

### Asking what you know

- **Ask Milo** (`Ctrl+Alt+M`): type a question, get the exact notes back
  with where each one came from and when. **He looks it up himself: no AI
  involved.** That means it's instant, it works offline, and it costs you
  nothing. He matches words, so a note has to say "code review" for a
  question about code review to find it.
- **Out loud**: hold the button in Milo's window and ask. He answers in his
  voice, with quotes.
- **`@milo`** in Copilot Chat: same thing, inside the chat you already
  use.
- **Milo's summary**: "what did we do yesterday", "the last hour", or
  "since your last summary". The list of what happened in memory, saved,
  and its headline spoken.
- **Milo's updates**: a glance in the Explorer at the last things that
  happened. Who saved what through which tool, what you approved, which
  brief went where.

### The Inbox: why you approve things

- **When *you* write a note, it's saved. Done.** No approval, it's your
  own words.
- **When an *AI tool* writes a note, it waits for you** in **Milo's
  Inbox**. You **Approve** it, **Edit** it and approve, or **Forget** it.
  You can also add a note for the team beside it.

That waiting is not a setting someone can flip by accident: it's built
into how saving works. The reason is simple: an AI should not be able to
quietly rewrite what your team believes is true.

If reviewing gets tiring, there's **Approve Everything in the Inbox**, and
an auto-approve switch if you decide you trust your tools. It warns you
first, honestly.

### Notes between your tools

Write a note that starts with `[Brief → Codex]` (or Claude Code, Gemini,
Kimi, Copilot) and what you want done. It waits in your Inbox like any
note. Any connected tool can read it through Milo's memory tools and answer
with a `[Report → you]` note the same way, and that lands in your Inbox
too. Milo never starts another program to deliver it.

### Privacy, concretely

- Nothing leaves your machine through Milo. There is no account and no
  server. Two things you can start hand text to other programs: Milo's
  voice goes to EchoVoice, and talking to Milo's brain goes to your own
  Copilot. Both are written out in the DISCLOSURES page.
- Nothing goes into your project's shared history (git) unless you turn
  that on. Three separate switches, all **off** to start.
- Your session digests, your notes about yourself, and any note you mark
  **Keep this from the tools** are **never** given to an AI model, even if
  it asks. Milo tells it to send you to look. A kept note stays out of
  `team.md` too; the file just says how many are kept.
- Uninstalling Milo **never deletes your memory.**
- If memory shows up from someone else's project, Milo asks you to read
  it before he trusts it.

### Milo and your other AI tools

Milo plugs into **Claude Code, Codex, Gemini CLI, Antigravity, and Kimi Code** in one
step, and he shows you exactly what he's about to change before he changes
it (and can undo it).

Inside VS Code with Copilot, Milo goes further:

- **Copilot's agent can ask Milo what the team decided, on its own**,
  while it works: VS Code asks your permission each time.
- **Copilot can hand Milo a note to remember**, which lands in your
  Inbox, waiting, like any AI's note.
- **`@milo`** answers in chat, using no AI and no tokens.

He can also leave a **small signpost** in `CLAUDE.md`, `AGENTS.md`, and
`GEMINI.md` (only if you say yes) that tells those tools where the memory
lives. A signpost, never your notes.

### Milo and your files

Those signpost files load before every conversation, so every line in them
costs you tokens every time. **Milo's receipt** tells you what they cost.
When one grows past the budget you set, Milo says so, your tool is asked to
propose the file's working core, and on your approval the original is kept
whole in `archive/` and the core becomes the file.

### The bottom bar

Bottom-right of VS Code, next to EchoAvatar: **EchoMemory**, and how many
things are waiting for you. Click it for the menu with every door.

Once in a while, after a long working session where nothing got written
down, he asks once if anything was worth remembering. Once. You can tell
him never to ask again and he won't.

### What Milo can NOT do today

Being straight about this so nobody promises it by mistake:

- **Milo cannot search `CLAUDE.md`, `AGENTS.md`, or `GEMINI.md`.** Those
  files belong to each AI tool. Milo measures them and can help put them on
  a diet, but he doesn't answer from them.
- **Milo does not use AI to answer Ask Milo.** That's deliberate. It's
  what makes him instant and free. The brain, when you hold the button and
  talk, is your own Copilot, and it only ever quotes memory.
- **Same machine only.** WSL, Remote-SSH, Dev Containers and Codespaces
  aren't supported in this release.

---

## What we're building next

**Planned as of 2026-10-01.**

### 1. Milo remembers without being asked, part three

Today the skills tell your tool to record decisions as it commits, and
Milo reads your commit messages. Next: at the end of a session, a digest is
proposed without anyone asking for it.

### 2. More words for Milo

"Where were we" in the morning. "Decision: X because Y" and "Lesson: X" as
their own quick notes. "Hand off" for the next window. Looking up a slash
command by voice. The Inbox by voice.

### 3. An EchoTools front door

One listing that installs the suite in a click, for people who come from
the website rather than a store page.

---

## Later: real possibilities, not commitments

- **Let Milo read the AI tools' files too**, so "search CLAUDE.md" becomes
  a thing he *can* do.
- **Search by meaning instead of words** (using a model running on your own
  machine, so it stays private and free): ask "that caching thing" and
  find the note that never used the word "caching".
- **Patterns over time**: "have we run into this before?" → "yes, three
  weeks ago, in this project, and here's what you did."

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
| **a brief**, **a report** | "dispatch", "job", "task" |

The engineering words still exist inside the code, where they belong. They
just never reach a screen, and there's an automatic check that fails the
build if one slips through.
