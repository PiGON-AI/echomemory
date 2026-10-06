# EchoMemory™: remember with your AI partner

You work with an AI coding partner. You decide things together, you fix a
hard bug at 2am. Next session, it remembers none of it, and neither does
the *other* AI tool you use. So you explain everything again, and pay for
those explanations every time.

**Milo remembers instead.** EchoMemory keeps a shared memory for your project
as plain markdown files you can open and read, and connects it to **Claude
Code, Codex, Gemini CLI, Antigravity, Kimi Code, and Copilot**, so every tool starts from
what the team already decided. Milo lives in **EchoAvatar** and speaks
through **EchoVoice**; EchoMemory is his memory, and the three install
together as the [EchoTools](https://echotools.dev) suite by PiGON AI.
**No telemetry, no server, no account. Nothing you write or ask ever leaves
your machine through us**; the one exception is the brain you choose for
talking to Milo, and the page below says exactly where that goes.

## Why EchoMemory

*Draft for Myriam's red pen.*

Your tools may each keep a memory of their own, and you may keep a pile of
instruction files. EchoMemory earns its place in five ways:

- **One memory for every tool.** A tool's built-in memory stays inside that
  tool. EchoMemory's memory sits in your project, and Claude Code, Codex,
  Gemini, Antigravity, Kimi Code and Copilot all read the same one. Decide
  something with one tool, and the next tool already knows.
- **You decide what is true.** Tools propose; you approve. Nothing a model
  writes becomes the team's memory until you say yes, so a tool can't quietly
  rewrite what your team believes.
- **Receipts, not promises.** Milo measures what your instruction and memory
  files cost your tools in tokens every session, and what they would cost
  without EchoMemory's compact view. Ask him for the receipt and he shows you
  the numbers from your own files.
- **Your tools work together.** A note that starts `[Brief → Codex]` is work
  you hand to a tool; the tool answers with a report. Tools from different
  companies share decisions through one memory you control.
- **It fills itself.** Finished sessions become digests, `Decision:` lines in
  your commits become notes, and Milo checks your repository's security on
  request. Everything stays on your machine; no account, no server.

## How it works

- **Where the memory lives:** in your project, in `.echomemory/`. Small text
  files, one per note, and a readable `team.md` that Milo rebuilds from
  them. Five tools can write at once and never scramble each other's work.
- **Saving:** **Pin & Note** from the menu · the `remember` skill in Claude
  Code, Codex or Kimi Code · ask any connected tool to save it · say "pin
  this" to Milo · or put a `Decision:` line in a commit message and Milo
  proposes it.
- **Asking:** **Ask Milo** (`Ctrl+Alt+M`): type a question, get the exact
  notes back with where each came from and when. **No AI involved**:
  instant, offline, free. Or `@milo` in Copilot Chat. Or hold the button in
  Milo's window and ask out loud.
- **your Inbox, why you approve things:** when *you* write a note, it's
  saved. When an *AI tool* writes one, it **waits for your OK**. That's built
  into how saving works, not a setting a tool can flip: an AI should never be
  able to quietly rewrite what your team believes is true. There's an
  **Approve Everything** button, and an auto-approve switch that warns you
  honestly first.
- **Milo's updates:** a glance in the Explorer at the last things that
  happened in this project's memory, newest first. Who saved what through
  which tool, what you approved, which brief went where.

## Getting started

1. Open the project you want Milo to remember and click **EchoMemory** on
   the bottom bar, next to EchoAvatar. The one-door card turns memory on,
   connects your tools, and shows your tools where memory lives, in one yes,
   with **What exactly changes** written out first. Everything stays local.
2. Restart each tool's session and it knows Milo.
3. Tell Milo what to call you (he asks once; it's skippable), save your
   first note, then ask him about it.

Each piece is also its own command if you'd rather go one step at a time:
**Turn On Memory for this Repo**, **Connect Milo to your AI Tools** (with a
preview of every file before it's touched, a backup first, and an undo),
and **Show My AI Tools Where Memory Lives** (a small signpost in `CLAUDE.md`,
`AGENTS.md` and `GEMINI.md`, and the three skills, each only if you tick it).

## About you, and how each tool works with you

**About you** asks four things, each skippable: what Milo should call you,
how much coding experience you have, how you like to work (warm and casual,
friendly and to the point, or direct and professional), and what you're
building. They live in your `user.md`, which your tools read, so a tool
explains things at your level and in your tone. What you're building also
goes to the team's memory, so the purpose stays in sight if the work drifts.

The first time each tool meets you, it introduces itself in a few lines,
proposes how you'll work together, and asks to save that agreement. On your
yes it lands in `user.md` under **How we work**, one agreement per tool.
Commands and tips you want to keep go under **Your toolkit**.

## Milo's summary and Milo's receipt

- **Milo's summary** ("what did we do yesterday", "the last hour", "since
  your last summary"): the ledger of what happened in memory, saved under
  `sessions/`, its headline spoken. No AI writes it; it's the records,
  arranged.
- **Milo's receipt**: what your convention files cost your tools every
  session, in tokens (an estimate, labeled as one), and what they'd cost raw.
  Saved beside
  the summaries so the trend is visible.
- **Milo's diet**: when a file grows past the budget you set, Milo's card
  says so, the tool you're working with is asked to propose the file's
  working core, and on your approval the original is archived untouched and
  the core becomes the file, with one line saying where the history lives.

## Notes between your tools

A note that starts `[Brief → Codex]` (or any tool) is an ordinary note: it
waits in your Inbox, any connected tool can read it through the memory
tools, and the tool can answer with a `[Report → you]` note the same way.

## Milo talks back

With EchoAvatar and EchoVoice (they install with this), hold the button in
Milo's window and talk. A question is answered from memory in Milo's voice,
quotes only. Say "pin this" and a card asks your yes. With a brain, Milo can
also open his doors for you: reads and his own body run on your word;
anything that writes memory comes back as a proposal and runs only on your
yes. Memory's quotes are verbatim and marked; the sentences around them are
the brain's.

Ask him how EchoMemory works, or for help with EchoVoice and EchoAvatar: he
answers from a guide that ships in the extension, written from these docs
and echotools.dev, and offers Milo's office (it opens right here in VS Code)
for anything deeper. Ask how much you have left: he gives Codex's limits and
opens Claude Code's own usage panel. Ask him to check your repository's
security: he runs a first pass and writes a brief your partners can act on.

**Milo's brain.** In VS Code it's your own Copilot. In editors without
Copilot (the Antigravity IDE, Cursor, Windsurf), or in VS Code if you prefer,
it's your own **Ollama**: a model downloaded on your machine, or Ollama's
hosted models with your API key. **Choose Milo's brain model** lists what you
have, small local models first, with the size and one line saying where your
words go; the key is kept in VS Code's secret store, never in settings. Small
local models are weaker at quoting and at opening doors than Copilot, and the
picker warns when a model doesn't advertise tool calling.

## Privacy, concretely

- **Nothing leaves your machine through us.** No account, no server, no
  telemetry. The doors that hand text to another program on your click
  (Milo's voice to EchoVoice; free speech and a brief to your own Copilot;
  free speech to the Ollama brain you chose, local or hosted) are named in
  [DISCLOSURES.md](DISCLOSURES.md), with where each one goes.
- **Nothing goes into your project's git history unless you turn it on**:
  three separate switches, all off to start, each with a preview.
- **Your session digests, your notes about yourself, and any note you mark
  "Keep this from the tools" are never handed to an AI model**, even if it
  asks. Milo tells it to send you to look instead. A kept note stays out of
  `team.md` too, and the file says how many are kept.
- Memory that shows up from someone else's clone or pull is **inert until
  you've read it**. Milo asks once, and "not now" is a real answer.
- **Uninstalling never deletes your memory.**

The complete list of every file EchoMemory writes, the exact entries it
adds to your tools' configuration files, and everything it runs or hands on
is in [DISCLOSURES.md](DISCLOSURES.md). If that page and the code ever
disagree, that's a bug: tell us.

## Commands

| Command | What it does |
| --- | --- |
| EchoMemory: Open Menu | Every door, from the bottom bar |
| EchoMemory: Open Milo's Memory | The Inbox: approve, edit, forget, add a note for the team |
| EchoMemory: Guided Setup | The one-door card: enable, connect, signposts, in one yes |
| EchoMemory: Turn On Memory for this Repo | Create `.echomemory/` (local, gitignored) |
| EchoMemory: Pin & Note | Save a note in your own words |
| EchoMemory: Ask Milo (`Ctrl+Alt+M`) | Look something up: quotes with sources, no AI |
| EchoMemory: Milo's summary | What happened in memory, since the last summary or in a time window |
| EchoMemory: What did we do yesterday? | The same, for yesterday |
| EchoMemory: Milo's receipt | What your files cost your tools, measured |
| EchoMemory: Milo's security check | A first pass over your repository, written as a brief for your partners' deep dive |
| EchoMemory: Show my Claude Code usage | Opens Claude Code's own panel, where Account and Usage shows the live numbers |
| EchoMemory: What should Milo call you? | Your name on your notes, and in his greeting |
| EchoMemory: Forget a note… | A note stops rendering and recalling; the record stays as history |
| EchoMemory: Connect Milo to your AI Tools | Register the memory server with Claude Code, Codex, Gemini CLI, Antigravity, Kimi Code, preview first |
| EchoMemory: Disconnect Milo from your AI Tools | Remove exactly what Connect wrote; memory untouched |
| EchoMemory: Show My AI Tools Where Memory Lives | Offer the signposts and the three skills, per file |
| EchoMemory: What Does Milo Remember? | A readable page of everything he keeps here |
| EchoMemory: Choose Milo's brain model | Pick the Ollama model Milo thinks with; size and where it runs shown |
| EchoMemory: Set / Clear Ollama API key | For Ollama's hosted models; kept in the secret store |
| EchoMemory: Approve Everything in the Inbox | Batch-approve waiting notes |
| EchoMemory: Auto-Approve / Review Myself | Skip the Inbox (with a warning) or use it |

## Settings

| Setting | Default | Meaning |
| --- | --- | --- |
| `echomemory.teamView` | `compact` | How `team.md` reads: headline and why per note (compact), or every note whole (full). Compact is the diet |
| `echomemory.brainProvider` | `auto` | Milo's brain for the button: Copilot when the editor has it, otherwise your Ollama; or pin one |
| `echomemory.brainHost` | `http://127.0.0.1:11434` | Where your Ollama answers. Keep it on this machine unless you know the host |
| `echomemory.brainModel` | empty | The Ollama model, set by Choose Milo's brain model |
| `echomemory.brainRoute` | `local` | Through your Ollama (local) or Ollama's servers with your key (hosted); set by the picker |
| `echomemory.rememberFromCommits` | `true` | A commit whose message has a `Decision:`, `Ruling:` or `Lesson:` line proposes that line in your Inbox, quoting the commit. Off: commits are never read |
| `echomemory.commitTeamEntries` | `false` | Commit `entries/` to git: shares approved notes with everyone who can read the remote |
| `echomemory.commitSessionDigests` | `false` | Commit `sessions/`: shares your session summaries and receipts |
| `echomemory.commitUserOverlay` | `false` | Commit your repo preferences (`user/`, `user.md`): shares how you personally work |

## Skills for your tools

**Show My AI Tools Where Memory Lives** offers three skills, written as each
tool reads them natively: `remember`, `digest` and `diet`, for Claude Code
(`.claude/skills/`), Codex (`.agents/skills/`) and Kimi Code
(`.kimi-code/skills/`). Each one ends the same way: the note waits in Milo's
Inbox. They also tell the tool to record a decision in the same breath as
the commit, and to put a `Decision:` line in the commit body so Milo
proposes it even when nobody says "remember".

## What Milo can't do yet

Being straight, so nobody promises it by mistake: Ask Milo matches the
words in your notes, so a note has to say "code review pass" for "did we do
a code review pass" to find it; he can't search `CLAUDE.md` or `AGENTS.md`
themselves (they belong to each tool); Kimi Code and Antigravity can't take a brief in the
background yet; Gemini means Gemini CLI (Code Assist, Cloud and API-key
accounts); and WSL, Remote-SSH, Dev Containers, and Codespaces aren't
supported in this release.

## The suite

EchoMemory is Milo's memory. It installs with Milo himself (EchoAvatar, about
48 MB) and his voice (EchoVoice), because the three are one companion.
EchoVoice works on its own; EchoAvatar needs EchoVoice; EchoMemory needs
both. VS Code will not uninstall EchoVoice or EchoAvatar while EchoMemory is
installed, and will say so.

## For AI assistants reading this package

This package includes [`llms.txt`](llms.txt), a briefing for AI models, and
[`AI-PARTNER.md`](AI-PARTNER.md), a guide your own AI partner can use to help
you set up and to describe Milo honestly.

## Support Milo

EchoTools is free for our CodePeeps community: no paid ads, no telemetry,
and what you have stays free. If Milo helps your workflows and coding
sessions, **[buy us a coffee ☕](https://buymeacoffee.com/pigon)**. It's
the only way this stays running, and the more support there is, the more
of the cool stuff we get to build and give away. Ideas are super welcome
too: **[💡 Suggest an idea](https://github.com/PiGON-AI/EchoMemory/issues/new?template=idea.yml)**.

## License

MIT © PiGON AI LLC. See [LICENSE](LICENSE) and
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). EchoMemory™ and Milo are
marks of PiGON AI LLC. Product names of the AI tools are used only to state
compatibility.
