# DISCLOSURES: every file, every switch, in one place

This page itemizes everything EchoMemory writes on your machine, everything
it hands to another program, what it never does, and the platform limits you
might hit. It describes **this release as shipped**; each release's
disclosures describe that release. If you find this page and the code in
disagreement, that's a bug: [tell us](https://github.com/PiGON-AI/EchoMemory/issues).

EchoMemory is different from its siblings in one honest way: EchoVoice and
EchoAvatar *read* and *play*. EchoMemory **writes**: your notes, into your
project. So this page is mostly a write-list, and every line of it is gated
by a choice you make.

## Network: none, except the brain you choose

EchoMemory has no telemetry, no analytics, no update check, no download.
Your notes, the Inbox, Ask Milo and the summaries make no network connection
at all; the guide Milo answers from ships inside the package. Nothing you
write, save, approve, or ask ever leaves your machine through us.

One file in the extension can open a connection, and only when you talk to
Milo with an **Ollama** brain (see **Milo's brain** below): it speaks to the
Ollama host you set (this machine by default) and, only if you stored an
Ollama API key, to `ollama.com`. A guard fails the package if network code
appears anywhere else.

The other things *you* can start that leave the machine, through programs that
are not us, are named in **What leaves your machine, and through whom** below.

## No AI tool is connected to your notes

EchoMemory registers no MCP server and writes no `CLAUDE.md`, `AGENTS.md` or
`GEMINI.md` block, no skills folder and no hook. It does not read your commits
or your tools' conversations. A tool reads `.milo/` only if you ask it to, like
any other folder in your project.

Two things do touch your AI coding tools, both optional and both in the
Storage table below:

- **The session-limit step** adds one status-line step to Claude Code's
  settings (`~/.claude/settings.json`), only after you answer **Watch it**, and
  puts your own status line back when you stop it or uninstall.
- **Your usage**: when you ask how much you have left, Milo reads the limit
  numbers Codex writes into its own session files under `~/.codex/sessions/`.
  Only those numbers, only then.

Notes that arrived from someone else's copy of the project (a `.milo/` folder
you didn't make) are never read to any brain until you have checked and
trusted them. Milo's brain settings are read from your own user settings only,
never from a project's `.vscode/settings.json`, so a project cannot change
where your words go.

## Milo's brain

Talking to Milo has two layers. A plain time or date question ("what time is
it") is answered by your machine's clock with no AI at all. Everything else
goes to a brain, and which brain depends on your editor and your settings:

- **Copilot** (the default in VS Code): your own Copilot model through VS
  Code's language-model API, under VS Code's own consent dialog and your plan.
  What goes: your sentence, the last three exchanges of this conversation (kept
  in memory for ten quiet minutes, never written anywhere), your newest notes
  (printed from his records, as `notes.md` shows them), Milo's doors and control words, and whatever Milo's
  read-only tools return when the brain calls them (see **What leaves your
  machine** below: your notes, the command guide, and the names and scripts of
  your repository, never a file's contents). Which Copilot model: the one you
  name in `echomemory.copilotModel` (by its family or name, as the Output
  channel lists them), or, if you name none, the model Copilot gives
  extensions by default. On a paid plan each turn spends your Copilot AI
  credits at that model's price; a turn that uses tools sends the prompt more than once.
  Nothing is stored by us. If you also chose an Ollama model, Milo falls back
  to it when Copilot is out of credits or has no model in this window, and
  says so in the Output channel; the same text then goes where that model runs.
- **Ollama, a local model** (the default where there is no Copilot: the
  Antigravity IDE, Cursor, Windsurf, or VS Code if you choose it): the same
  text goes to your Ollama at `echomemory.brainHost`, `http://127.0.0.1:11434`
  unless you change it. A model whose name ends in `-cloud` runs on Ollama's
  servers through your local Ollama, and the picker says so.
- **Ollama, hosted**: the same text goes to Ollama's servers with the API key
  you stored. The key lives in VS Code's **secret store** on this machine,
  never in a settings file (settings sync and get shared); **Set Ollama API
  key** stores it and **Clear Ollama API key** removes it.

The brain is also told the real date and time from your machine's clock, with
your time zone's name ("Saturday, October 3, 2026, 9:28 am Pacific Time"), so
"good morning" and "today" mean what they say. It is told nothing about where
you are; the time zone is as close as Milo gets, on purpose.

Which brain is on is never hidden: Milo's strip in EchoAvatar's window says
"brain on" with the brain in brackets, Copilot, Ollama local or Ollama cloud,
and every answer in the Output channel names the brain that gave it. All
three are your own; Copilot and Ollama cloud send your words off the machine,
Ollama local keeps them on it.

**Choose Milo's brain model** lists the models your Ollama has and, with a
key, the hosted ones. A **Recommended** line at the top names one model and
its price in plain words (a hosted 20B-class model when you have a key: fast,
words leave the machine like Copilot's; otherwise the local model nearest
8 GB: private, slower); nothing is chosen for you. Below it, every model with
its size and one line saying where your words go. A model that does not
advertise tool calling gets a warning: Milo can answer with it but may not be
able to open his doors. Whatever the brain, the rules hold: anything Milo
says about your notes comes only from what his tools returned, naming the
note it came from; reads and Milo's body run on your word; a note in your own
words, an approval or a forget comes back as a proposal and runs only on your
yes; a note Milo writes for you waits in your Inbox; and if the brain returns
nothing usable, a fixed line is spoken rather than an invention. If the brain
says it did something but no door ran, Milo replaces its sentence with the
truth. Small local models are weaker at quoting and at calling tools than
Copilot; we say so here rather than let you find out.

When you turn Milo's brain on, EchoAvatar asks first, in these words, the same
sentence this page stands behind:

> Your words are turned into text on your machine. When his brain is on, that text goes to the model you chose for his brain (Copilot in VS Code, or Ollama, on your computer or in Ollama's cloud), together with what Milo needs to answer: your saved notes, today's date and time, EchoTools' guides, and, only when a question needs them, your project's file and script names, its own commands and skills, and your usage numbers. Nothing else leaves.

The notes Milo hands the brain are printed from his records, never read off
`notes.md` on disk, so editing that page changes nothing the brain sees.

## The suite

EchoMemory is Milo's memory. It installs with Milo himself (EchoAvatar) and
his voice (EchoVoice), because the three are one companion. The manifest
declares both as dependencies, so the store installs them with it, and VS Code
will refuse to uninstall EchoVoice or EchoAvatar while EchoMemory is
installed, and will name it. There is no memory-only mode and no switch to
turn the voice or the body off from here: EchoVoice alone, EchoVoice with
EchoAvatar, or all three.

## Storage: what's on your disk, when it gets there, and how to remove it

Nothing below exists until the action in the **when** column happens.

| what | where | when | remove it |
|---|---|---|---|
| **Your notes.** `entries/` (one small file per note, append-only; an approve or a forget is its own file, so history is never rewritten), `notes.md` (a readable page Milo prints from the records; never the source of truth, and editing it changes nothing he remembers), `sessions/` (Milo's summaries), `runtime/` (locks, operation ids, `misses.jsonl` (each question Milo could not answer or do, with his reply, so you can see what he should learn next; it never leaves the machine), `ratings.jsonl` (each 👍 or 👎 you give an answer, with the question, the answer and the brain), and `quarantine/` for a corrupt record set aside, never silently dropped). Every record carries **who wrote it** (the name you told Milo for your own notes, or "you", never your operating-system login; "Milo" for a note he proposed) and **when** | `<your project>/.milo/` | Only after you turn memory on for that project | Delete the folder. EchoMemory never deletes your notes: not on uninstall, not on Forget (a forgotten note stays as history and stops showing and recalling) |
| **Milo's two caches.** `tldr/` (a short TL;DR of `notes.md` or the newest summary, written by your brain the first time you ask for one and reused until the notes change; it is never treated as one of your notes) and `answers/` (Milo's answers to command questions built purely from the shipped guide, recycled when the same question comes again; never an answer that read your notes, the Inbox, the clock or your repository; cleared when the guide changes, and an answer you rate 👎 is removed). They live outside your project on purpose, so a repository can never carry one in | VS Code's storage for this extension, one folder per project (`caches/<project>/`) | The first time Milo needs one | Uninstalling the extension |
| **`.milo/.gitignore`**, one line, `*`: the folder ignores itself, every file in it, so nothing in `.milo/` is committed. Your own `.gitignore` is never touched | inside `.milo/` | When memory is turned on | Removing it would let git see your notes |
| **`.milo/.gitattributes`** (`* text eol=lf`): records are written with LF and compared byte for byte | inside `.milo/` | With the `.gitignore` | Leave it |
| **Milo's security first pass.** On request only ("check my repo", or **Milo's security check** in the menu), Milo reads your repository the way git lists it: the names of tracked files, and the text of small tracked text files, looking for committed secret files and secret-shaped text, a `.gitignore` that misses `.env`, a lockfile, a security policy, and risky GitHub Actions settings. No AI, nothing sent anywhere. A secret's value is never written down, only the file and line where something secret-shaped appears. The result is a report that waits in your Inbox | The report, as a note in `.milo/` | Only when you ask | Forget the note |
| **Milo's notes for you.** When you ask Milo to remember what you just told him, or to summarize one of your notes, the brain writes a few lines and Milo files them as a **proposal**: it waits in your Inbox, and only counts once you approve it | A note in `.milo/` | Only when you ask | Forget it in your Inbox |
| **Your usage, when it's asked for.** When you ask Milo how much you have left: the newest limit numbers Codex wrote into its own session files under `~/.codex/sessions/` (percent used and reset time per window), and the numbers the session-limit step saved, if it is on. For Claude Code, Milo opens Claude Code's own panel, where **Account and Usage** shows the live numbers; he never reads Claude Code's login or tokens. EchoAvatar's break check-ins at three and five hours may ask for one line of the same Codex numbers and offer a **Check Claude usage** button. Read only; nothing leaves your machine | Nothing new: these are read where Codex and the step already keep them | Only when you ask, or click the button | Nothing to remove |
| **The session-limit step (Claude Code).** A small script that Claude Code runs as its status line: it saves the session-limit numbers Claude Code gives a status line on a Pro or Max seat (the five-hour and seven-day percentages and their reset times) to `~/.echomemory/usage/claude-code.json`, then runs the status line you had before, with the same input, so it keeps showing. Milo reads that file and gives one heads-up at 85%, 90% and 95% of the five-hour window, with the time to reset; with no number, he says nothing (he never estimates a limit). Nothing leaves your machine | The script and `chain.json` (your previous status line) in `~/.echomemory/statusline/`; the `statusLine` entry in `~/.claude/settings.json`; the numbers in `~/.echomemory/usage/` | Only after you answer **Watch it** to one plain question (offered once, or **Watch my Claude Code session limit** in the command palette). Settings that cannot be read as JSON are never rewritten | **Stop watching my session limit** puts your own status line back exactly; uninstall does the same |
| **Your name.** What you told Milo to call you | the editor's global state for this extension, on this machine only | When you answer Milo's question (skippable) | **What should Milo call you?** in the menu |
| **The uninstall log.** A plain-text line saying whether the uninstall put your Claude Code status line back | `~/.echomemory/uninstall.log` | After uninstall | Delete it |
| **Trust and small state.** Per-project trust ledger (a revision id, the record ids and a fingerprint of each record, so a note changed outside EchoMemory is noticed; never note content) and the nudge timestamps | the editor's extension state store | As you use the product | Uninstalling the extension; nothing here carries content |

## What leaves your machine, and through whom

EchoMemory itself sends nothing anywhere. These doors you open hand text to
programs that may:

- **Milo's voice.** Every line Milo speaks is handed, as text, to the
  installed **EchoVoice** through its `speakText` command, with `source:
  "milo"` so you can mute or voice Milo apart from your partners. What
  EchoVoice does with that text (local engines, or ElevenLabs if you chose
  it) is in EchoVoice's own DISCLOSURES.
- **Milo talks back** (the button and bar in EchoAvatar's window). A plain
  time or date question is answered by the clock with no AI at all. Everything
  else is handed to **the brain you chose** (see **Milo's brain**). What goes:
  your sentence, the last three exchanges of this conversation, your newest
  notes (printed from his records, up to 16,000 characters), the list of doors Milo may
  open, and the control words. The brain may then call read-only tools, and
  what they return goes to it too: **memory_query** (a list of your notes by
  kind, state and time: id, who, when, state, first line), **memory_read**
  (one note's full text, `notes.md`, or the newest summary),
  **command_lookup** (the shipped command guide and your repository's own
  commands and skills), **repo_glance** (your
  repository's top-level folder and file names, `package.json` script names,
  the most common file types, and which AI tool conventions exist: names
  only, never a file's contents), **session_usage** (your usage numbers, as
  above), **support_lookup** (Milo's guide, which ships in the extension: how
  EchoMemory works, generated from its own README and WHAT-MILO-DOES, and
  basic EchoTools tech support, generated from the same knowledge Milo uses on
  echotools.dev), and **offer_link** (a button to one of the team's links, by
  name; see **Milo's link buttons**). One more tool, `milo_do`, opens one door
  from a closed list: reads and Milo's body run on your word; a note in your
  own words, an approval or a forget comes back as a **proposal** and runs only
  on your yes; a note Milo writes for you waits in your Inbox.
- **"I can't do that yet."** When you ask Milo to do something no door can
  do, he says so, and once per window offers the team's address,
  `milo@echotools.dev`. If you choose **write it up**, EchoMemory asks your
  operating system to open your own mail app with a draft (your question
  only, nothing from your notes) and copies the address to your clipboard. We
  send nothing: the email leaves only if you press Send in your mail app.
- **What Milo remembers while you talk to him.** In memory only: your last
  three exchanges (forgotten after ten quiet minutes) and the questions you
  asked this VS Code session (gone when VS Code closes), so he can connect
  what you asked before to what might help next. Two files on your machine do
  keep a question: `misses.jsonl` when Milo couldn't answer it, and
  `ratings.jsonl` when you rated his answer (see Storage). Neither leaves your
  machine.
- **Milo's link buttons.** When you ask for tech support, how to report a
  problem, where to leave a review, how to support the team, or where to
  follow along, Milo may offer a button. He never opens a link himself: only
  your click does, in VS Code's own browser tab where the editor has one, and
  otherwise in your operating system's browser. Reporting a problem and the
  store reviews always open in your own browser, where you are signed in; VS
  Code may ask first. **Report a problem** fills in your EchoMemory version,
  your editor and your operating system's name in the GitHub form, as
  EchoVoice and EchoAvatar do; you see them before you submit, and the log is
  never filled in. The brain can only name a link from a fixed list that ships
  in the extension; the address always comes from that list, never from a
  brain or a note. The list: echotools.dev, the EchoTools issues page on
  GitHub (`github.com/PiGON-AI/echotools/issues`), the EchoVoice and EchoAvatar
  review pages on the Visual Studio Marketplace and Open VSX, Buy Me a Coffee
  (`buymeacoffee.com/pigon`), and the Code Peeps and PokieVault Instagram
  pages. What those sites do once you are there is theirs, not ours.

## Platform notes: the kinks, up front

- **Same machine only, in this release.** **WSL, Remote-SSH, Dev Containers,
  and Codespaces are not supported yet.** Named here so you find it in the
  docs, not in the field.
- **Ask Milo uses no AI.** It looks notes up by the words in them. That is
  why it's instant, free, and offline, and why it answers with quotes, never
  conclusions, and why a note has to say "code review pass" for the question
  "did we do a code review pass" to find it.
- **Milo talks back** needs VS Code 1.101 or newer with Copilot signed in, or
  your own Ollama; without a brain, Milo says so in one fixed sentence when you
  press the button.
- **Windows and macOS.** A Mac is tested by the crew before each ship;
  nothing here is Windows-only by design.
- **Uninstalling never deletes your notes.** Your notes are yours; an
  uninstall is not a request to forget.

## Affiliation

EchoMemory is an independent project by PiGON AI. It works alongside the AI
coding tools you've installed; it is not affiliated with, sponsored by, or
endorsed by Anthropic, OpenAI, Google, Microsoft, or Moonshot AI. Product
names are used only to state compatibility.

## Provenance

EchoMemory is built as a human and AI partnership. See `llms.txt` for the
briefing we ship for AI models. Contact: milo@echotools.dev (read by both
partners).
