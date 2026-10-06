# DISCLOSURES: every file, every switch, in one place

This page itemizes everything EchoMemory writes on your machine, everything
it hands to another program, what it never does, and the platform limits you
might hit. It describes **this release as shipped**; each release's
disclosures describe that release. If you find this page and the code in
disagreement, that's a bug: [tell us](https://github.com/PiGON-AI/EchoMemory/issues).

EchoMemory is different from its siblings in one honest way: EchoVoice and
EchoAvatar *read* and *play*. EchoMemory **writes**: into your repository,
and, only if you ask, into your AI tools' configuration files. It can also
**run** one of your AI tools for you, in a copy of your repository, on your
click. So this page is mostly a write-list and a run-list, and every line of
it is gated by a choice you make.

## Network: none, except the brain you choose

EchoMemory has no telemetry, no analytics, no update check, no download.
Memory, the Inbox, Ask Milo, the summaries, the receipts and the MCP server
make no network connection at all; the knowledge base
Milo answers from ships inside the package. Nothing you write, save, approve,
or ask ever leaves your machine through us.

One file in the extension can open a connection, and only when you talk to
Milo on the button with an **Ollama** brain (see **Milo's brain** below): it
speaks to the Ollama host you set (this machine by default) and, only if you
stored an Ollama API key, to `ollama.com`. A guard fails the package if
network code appears anywhere else.

The other things *you* can start that leave the machine, through programs that
are not us, are named in **What leaves your machine, and through whom** below.

## Milo's brain

Talking to Milo on the button has two layers. A plain time or date question
("what time is it") is answered by your machine's clock with no AI at all.
Everything else goes to a brain, and which brain depends on your editor and
your settings:

- **Copilot** (the default in VS Code): your own Copilot model through VS
  Code's language-model API, under VS Code's own consent dialog and your plan.
  What goes: your sentence, the last three exchanges of this conversation (kept
  in memory for ten quiet minutes, never written anywhere), the newest notes of
  the compact `team.md`, Milo's doors and control words, and
  whatever Milo's read-only tools return when the brain calls them (see **Milo
  talks back** below: memory notes, `user.md`, the command guide, and the names
  and scripts of your repository, never a file's contents). Which Copilot
  model: the one you name in `echomemory.copilotModel` (for example
  `gpt-5-mini`), or, if you name none, the model Copilot gives extensions by
  default (on Copilot Free, GPT-4o mini). On a paid plan each turn spends
  your Copilot AI credits at that model's price; a turn that uses tools sends
  the prompt more than once. Nothing is stored by us. If you
  also chose an Ollama model, Milo falls back to it when Copilot is out of
  credits or has no model in this window, and says so in the Output channel;
  the same text then goes where that model runs.
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
three are the person's own; Copilot and Ollama cloud send your words off the
machine, Ollama local keeps them on it.

**Choose Milo's brain model** lists the models your Ollama has and, with a
key, the hosted ones. A **Recommended** line at the top names one model and
its price in plain words (a hosted 20B-class model when you have a key: fast,
words leave the machine like Copilot's; otherwise the local model nearest
8 GB: private, slower); nothing is chosen for you. Below it, every model with
its size and one line saying where your words go. A model that does not advertise tool calling
gets a warning: Milo can answer with it but may not be able to open his
doors. Whatever the brain, the rules hold: a decision is quoted word for word
and marked; anything else (a summary, a date, which brief came last) is said
in the brain's own words, only from what Milo's tools returned, naming the
note it came from; reads and Milo's body run on your word, anything that
writes memory comes back as a proposal, and if the brain returns nothing
usable, memory's own fixed line is spoken rather than an invention. If the
brain says it did something but no door ran, Milo replaces its sentence with
the truth. Small local models are weaker at quoting and at calling tools than
Copilot; we say so here rather than let you find out.

## The suite

EchoMemory is Milo's memory. It installs with Milo himself (EchoAvatar, about
48 MB) and his voice (EchoVoice), because the three are one companion. The
manifest declares both as dependencies, so the store installs them with it,
and VS Code will refuse to uninstall EchoVoice or EchoAvatar while EchoMemory
is installed, and will name it. There is no memory-only mode and no switch to
turn the voice or the body off from here: EchoVoice alone, EchoVoice with
EchoAvatar, or all three.

## Storage: what's on your disk, when it gets there, and how to remove it

Nothing below exists until the action in the **when** column happens.

| what | where | when | remove it |
|---|---|---|---|
| **Your repository's memory.** `entries/` (one small file per team note, append-only; a transition such as approve or forget is its own file, so history is never rewritten), `user/` (your notes about yourself for this repository, same shape), `team.md` and `user.md` (readable views rebuilt from the records; never the source of truth), `sessions/` (session digests, Milo's summaries, Milo's receipts), `archive/` (a file's full text, byte for byte, when you approve Milo's diet for it), `runtime/` (locks, handshake ledgers, operation ids, announcement markers, `misses.jsonl` (each question Milo could not answer or do, with his reply, so you can see what he should learn next; it never leaves the machine), `tldr/` (a short TL;DR of `team.md`, `user.md` or the newest summary, written by your brain the first time you ask for one and reused until that file changes; each names the model that wrote it and is never treated as a decision), `answers/` (Milo's answers to command questions built purely from the shipped guide, recycled when the same question comes again; never an answer that read your notes, the Inbox, the clock or your repository; cleared when the guide changes, and an answer you rate 👎 is removed), `ratings.jsonl` (each 👍 or 👎 you give an answer, with the question, the answer and the brain; a 👎 also removes the TL;DRs that answer used), and `quarantine/` for a corrupt record set aside, never silently dropped), plus a managed `.gitignore` and `.gitattributes`. Every record carries **who wrote it** (the name you gave in About You for your own notes, never your operating-system login; the tool's name for a model's), **through which tool**, and **when**; that provenance travels with the record if you ever turn a commit switch on | `<your project>/.echomemory/` | Only after you answer **Enable memory** for that repository | Delete the folder. EchoMemory never deletes memory: not on Disconnect, not on uninstall, not on Forget (a forgotten note stays as history and stops rendering and recalling) |
| **The managed `.gitignore`.** The mechanism that makes "local by default" true: `entries/`, `sessions/`, `user/` and `user.md` stay out of git until you flip the matching setting **on**; `runtime/`, `team.md` and the quarantine are ignored always | inside `.echomemory/` | Written when memory is enabled; regenerated whenever a commit switch changes | Turning a switch back off tightens it again |
| **The managed `.gitattributes`** (`* text eol=lf`): records are written with LF and compared byte for byte; a CRLF checkout would change them | inside `.echomemory/` | With the `.gitignore` | Leave it; removing it breaks records on Windows checkouts |
| **Milo's security first pass.** On request only ("check my repo", or **Milo's security check** in the command palette), Milo reads your repository the way git lists it: the names of tracked files, and the text of small tracked text files, looking for committed secret files and secret-shaped text, a `.gitignore` that misses `.env`, a lockfile, a security policy, and risky GitHub Actions settings. No AI, nothing sent anywhere. A secret's value is never written down, only the file and line where something secret-shaped appears. The result is a `[Brief → all]` note that waits in your Inbox; once you approve it, your connected tools can read it like any note | The brief, as a team note in `.echomemory/` | Only when you ask | Forget the note |
| **Your usage, when it's asked for.** When you ask Milo how much you have left: the newest limit numbers Codex wrote into its own session files under `~/.codex/sessions/` (percent used and reset time per window), and the numbers the session-limit step saved, if it is on. For Claude Code, Milo opens Claude Code's own panel, where **Account and Usage** shows the live numbers; he never reads Claude Code's login or tokens. EchoAvatar's break check-ins at three and five hours may ask for one line of the same Codex numbers and offer a **Check Claude usage** button. Read only; nothing leaves your machine | Nothing new: these are read where Codex and the step already keep them | Only when you ask, or click the button | Nothing to remove |
| **The session-limit step (Claude Code).** A small script that Claude Code runs as its status line: it saves the session-limit numbers Claude Code gives a status line on a Pro or Max seat (the five-hour and seven-day percentages and their reset times) to `~/.echomemory/usage/claude-code.json`, then runs the status line you had before, with the same input, so it keeps showing. Milo reads that file and gives one heads-up at 85%, 90% and 95% of the five-hour window, with the time to reset; with no number, he says nothing (he never estimates a limit). Nothing leaves your machine | The script and `chain.json` (your previous status line) in `~/.echomemory/statusline/`; the `statusLine` entry in `~/.claude/settings.json`; the numbers in `~/.echomemory/usage/` | Only after you answer **Watch it** to one plain question (offered once, or **Watch my Claude Code session limit** in the command palette). Settings that cannot be read as JSON are never rewritten | **Stop watching my session limit** puts your own status line back exactly; uninstall does the same |
| **A memory pointer.** One clearly marked block telling your AI tools where memory lives (a signpost, never your notes). For Claude Code and Gemini the block imports `team.md` and `user.md` so they preload the compact view each session; for the tools that read `AGENTS.md` (Codex, Kimi Code, Copilot) it says to read `team.md` first | `CLAUDE.md`, `AGENTS.md`, `GEMINI.md` in your project; existing files are updated; a file is **created** only if you tick that line | Only the files you tick in **Show my AI tools where memory lives**; a block you deleted is offered back, never forced back | Delete the block, or run Disconnect or uninstall, which remove only what they wrote |
| **Three skills for three tools.** `remember`, `digest` and `diet`, as skill folders each tool reads natively | `.claude/skills/<name>/SKILL.md` (Claude Code), `.agents/skills/<name>/SKILL.md` (Codex), `.kimi-code/skills/<name>/SKILL.md` (Kimi Code), in your project | Only if you tick them in the same dialog. The July build's two slash commands under `.claude/commands/` are offered for removal when the skills are written | Delete the folders |
| **Your name.** The name you gave in About You | the editor's global state for this extension, and as a user-scope record in each repository where you said it | When you answer Milo's question (skippable) | Clear it from About You; delete the record |
| **The uninstall manifest and log.** Which AI-tool configs hold our entry, so a true uninstall can clean up after the extension is gone; a plain-text log of what it did. One manifest **per editor** (VS Code and a fork such as Cursor or the Antigravity IDE each keep their own), so uninstalling EchoMemory in one editor never removes another editor's registrations; the uninstall script also leaves any entry that points at a different editor's launcher | `~/.echomemory/uninstall/<editor key>.json`, `~/.echomemory/uninstall.log` | Manifest: after Connect. Log: after uninstall | Delete them |
| **The MCP server** your AI tools launch: the server bundle, a two-line launcher (`echomemory-mcp.cmd` on Windows, `.sh` elsewhere), `server-config.json` (which repository the tools' memory points at, plus the knowledge-base paths), and a `runtime/` lock folder | the editor's global storage folder for this extension (`mcp/`), a stable path, so an extension update never breaks a registration | On **Connect**. The bundle is checksummed (SHA-256) against the shipped copy on every connect and re-copied if it drifts | Uninstall removes the whole folder |
| **Trust and small state.** Per-repository trust ledger (a revision id and record ids, never note content), which repository the tools are connected to, the auto-approve flag, the per-repository consent for each commit switch, the last commit the commit watcher saw, and the nudge timestamps | the editor's extension state store | As you use the product | Uninstalling the extension; nothing here carries content |

## Your AI tools' configuration files: the one place we write outside your project

Only through **Connect Milo to your AI tools**, and only for the tools you
pick. Before anything is written you see a **preview document** listing each
file, the exact entry to be added, and the adapter's confidence; then a
modal asks once more. For each file: a timestamped **backup** is written
beside it first, the write is **atomic**, an **independent check** re-reads
the result (JSON configs; the Codex TOML has no independent parser, and the
report says so), and if that check fails the change **rolls back** on its
own. The entry is merged in. Nothing else in your config is rewritten.

| tool | file | what is added |
|---|---|---|
| Claude Code | `~/.claude.json` | one `mcpServers.echomemory` entry |
| Codex | `~/.codex/config.toml` | one owned `mcp_servers.echomemory` block, with `default_tools_approval_mode = "approve"` so Codex may call EchoMemory's tools without asking you each time (it still cannot write memory without your approval; see below) |
| Gemini CLI | `~/.gemini/settings.json` | one `mcpServers.echomemory` entry with `trust: true`, the same per-call waiver. Gemini CLI serves Gemini Code Assist, Google Cloud and API-key accounts; since 2026-06-18 it no longer serves free or individual Google accounts, which Google moved to Antigravity |
| Antigravity (the IDE and the `agy` command line share this file) | `~/.gemini/config/mcp_config.json` | one `mcpServers.echomemory` entry (command, arguments, environment), the same entry Antigravity's own `agy mcp add` writes; other servers you added through Antigravity's store are untouched |
| Kimi Code | `~/.kimi-code/mcp.json` | one `mcpServers.echomemory` entry |

An entry named `echomemory` that we did not write is **refused**, never
replaced. **Disconnect** removes exactly our entries; **uninstall** does the
same from the manifest, with a log. Inside VS Code, Milo is also offered to
Copilot through the editor's own MCP registry: no file is written for that.

EchoMemory installs **no hooks** into any tool. The session digest is a
skill you invoke; nothing watches your sessions or summarizes them behind
your back.

## What your AI tools can and cannot do through Milo

The MCP server offers four tools. Each declares whether it reads or writes.

- **`memory_recall`** (read) and **`team_status`** (read): approved team
  memory for the connected repository, as exact quotes with sources and
  when, never a summary Milo invented. Recall also returns the current
  revision so a later write can refuse if memory changed underneath it.
- **`memory_remember`** (write) and a status update through `team_status`
  (write): a note is **proposed**. A model's note lands in **your Inbox**
  and is not team truth until you approve it. This is enforced in the
  storage engine, not a setting a tool can flip. The only way around it is
  **Auto-Approve**, which you turn on yourself after a warning that says
  exactly what it restores, and which is one visible click to turn off.
- **`command_lookup`** (read): what a slash command does in Claude Code,
  Codex or Kimi Code, from the knowledge base shipped in the package.
- **Never** receive your session digests, your About You notes, or a note
  you marked **Keep this from the tools** through recall: those are withheld
  and counted, and Milo tells the tool to send you to look instead. A kept
  note never renders in `team.md` (which tools preload; the file says how
  many notes are kept), never appears in `team_status`, and is never spoken
  by Milo's voice; you read it in Milo's Memory. The mark is yours to set,
  on Pin & Note, and by voice ("pin this" with "keep it from the tools" is a
  proposal that waits for your yes). Every other team note is readable by
  every connected tool.
- **Never** read memory that arrived from someone else's clone or pull until
  you have reviewed and trusted it for that repository.

Redaction of secrets, paths, and personal details before anything is
committed is **best-effort**: a scanner, not a guarantee. The real safety is
that nothing is committed to git until you turn a switch on, with a preview.

## The commit watcher: Milo reads your commits

With `echomemory.rememberFromCommits` on (the default), EchoMemory watches
the repository's commit log (`.git/logs/HEAD`) and reads new commits with
`git log`. A commit whose message carries a line starting `Decision:`,
`Ruling:` or `Lesson:` proposes that line as a **pending** note in your
Inbox, quoting the commit hash. A commit without a marker proposes nothing.
The first time it sees a repository it records the current commit and
proposes nothing from history. It **reads** git and never writes it, never
runs a hook, and never touches your working tree. Turn the setting off and
commits are never read.

## Memory that fills itself: Milo reads your tools' transcripts

With `echomemory.captureSessions` on (the default), every five minutes Milo
looks at the transcripts **Claude Code** and **Codex** already write on this
machine for the repository you have open: Claude Code's project folder under
`~/.claude/projects/`, and Codex's rollouts under `~/.codex/sessions/` from
the last three days, matched by the session's own working folder. A
transcript that has been quiet for ten minutes is a finished session. If it
edited a file, made a commit, or carried a `Decision:`, `Ruling:` or
`Lesson:` line in a commit message, Milo files a **session digest** that
waits in your Inbox: when it ran, how many turns and commands, which files
were edited, the commit subjects, and the decision lines as written. No AI
writes it and no token is spent. A session that only read things proposes
nothing. Decisions are taken from commit messages only, never from the
conversation itself.

It **reads** those files and never writes, moves or deletes them; it
installs no hook; nothing it reads leaves your machine. The first time it
sees a repository it records the moment and captures nothing older. Like
every digest, a captured session is never handed to an AI tool through
recall. Turn the setting off and transcripts are never read for memory.

## What leaves your machine, and through whom

EchoMemory itself sends nothing anywhere. Two doors you open hand text to
programs that may:

- **Milo's voice.** Every line Milo speaks is handed, as text, to the
  installed **EchoVoice** through its `speakText` command, with `source:
  "milo"` so you can mute or voice Milo apart from your partners. What
  EchoVoice does with that text (local engines, or ElevenLabs if you chose
  it) is in EchoVoice's own DISCLOSURES.
- **Milo talks back** (the button in EchoAvatar's window). A plain time or
  date question is answered by the clock with no AI at all. Everything else
  is handed to **the brain you chose** (see **Milo's brain**): your own
  Copilot model through VS Code's language-model API, or your Ollama, local
  or hosted. What goes: your sentence (with Milo's name stripped before the
  memory search), the last three exchanges of this conversation, the
  compact `team.md` without Milo's summary pointers (its newest notes, up to
  16,000 characters), the list of doors Milo may open, and the control words. The
  brain may then call read-only tools, and what they return goes to it too:
  **memory_query** (a list of notes by kind, author, state and time: id,
  who, when, state, first line), **memory_read** (one note's full text, the
  newest of a kind, `team.md` or `user.md`), **recall** (a word search of
  approved memory), **command_lookup** (the shipped command guide and your
  repository's own commands and skills), and **repo_glance** (your
  repository's top-level folder and file names, `package.json` script names,
  the most common file types, and which AI tool conventions exist: names
  only, never a file's contents), **support_lookup** (Milo's guide, which ships in the extension: how EchoMemory works, generated from its own README and WHAT-MILO-DOES, and basic EchoTools tech support, generated from the same knowledge Milo uses on echotools.dev), and **offer_link** (a button to one of the
  team's links, by name; see **Milo's link buttons**). A note you marked "keep this from the
  tools" is never returned by any of them; they say how many they withheld.
  A note from outside that you have not trusted is listed by state only,
  its words withheld. One more tool, `milo_do`, opens one door from a closed
  list: reads and Milo's body run on your word; anything that writes memory
  comes back as a **proposal** and runs only on your yes. A decision is
  quoted word for word and marked; the other sentences are the brain's,
  built only from what the tools returned.
- **"I can't do that yet."** When you ask Milo to do something no door can
  do, he says so, and once per window offers the team's address,
  `milo@echotools.dev`. If you choose **write it up**, EchoMemory asks your
  operating system to open your own mail app with a draft (your question
  only, nothing from memory) and copies the address to your clipboard. We
  send nothing: the email leaves only if you press Send in your mail app.
- **Milo's link buttons.** When you ask for tech support, how to report a
  problem, where to leave a review, how to support the team, or where to
  follow along, Milo may offer a button. He never opens a link himself: only
  your click does, in VS Code's own browser tab where the editor has one, and
  otherwise in your operating system's browser; VS Code may ask first. The brain can only name a link from a fixed list that ships in
  the extension; the address always comes from that list, never from a brain
  or a note. The list: echotools.dev, the EchoTools issues page on GitHub
  (`github.com/PiGON-AI/echotools/issues`), the EchoVoice and EchoAvatar
  review pages on the Visual Studio Marketplace and Open VSX, Buy Me a Coffee
  (`buymeacoffee.com/pigon`), and the Code Peeps and PokieVault Instagram
  pages. What those sites do once you are there is theirs, not ours.
## Notes between your tools

A note that starts `[Brief → Codex]` (or any tool) is an ordinary note: it
waits in your Inbox like any other, any connected tool can read it through
the memory tools, and a tool can file its answer as a `[Report → you]` note
the same way. EchoMemory never starts another program to deliver it.

## Platform notes: the kinks, up front

- **Same machine only, in this release.** VS Code and your AI tools must run
  on the same operating system and filesystem. **WSL, Remote-SSH, Dev
  Containers, and Codespaces are not supported yet**: the tools would look
  for memory on a different machine than the editor. Named here so you find
  it in the docs, not in the field.
- **Ask Milo uses no AI.** It looks notes up by the words in them. That is
  why it's instant, free, and offline, and why it answers with quotes, never
  conclusions, and why a note has to say "code review pass" for the question
  "did we do a code review pass" to find it.
- **Copilot features** (`@milo` in chat, the two agent tools, the MCP offer,
  Milo talks back) need VS Code 1.101 or newer and
  Copilot signed in; without Copilot they simply don't appear, and Milo says
  so in one fixed sentence when you press the button.
- **Windows and macOS.** A Mac is tested by the crew before each ship;
  nothing here is Windows-only by design.
- **Uninstalling never deletes memory.** Your notes are yours; an uninstall
  is not a request to forget.

## Affiliation

EchoMemory is an independent project by PiGON AI. It works alongside the AI
coding tools you've installed; it is not affiliated with, sponsored by, or
endorsed by Anthropic, OpenAI, Google, Microsoft, or Moonshot AI. Product
names are used only to state compatibility.

## Provenance

EchoMemory is built as a human and AI partnership. See `llms.txt` for the
briefing we ship for AI models, and `AI-PARTNER.md` for the guide your own
AI assistant can use to help you set up. Contact: milo@echotools.dev (read by
both partners).
