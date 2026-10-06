# EchoMemory: Troubleshooting

First stop, always: **View > Output > pick "EchoMemory"** in the dropdown.
Milo narrates every enable, connect, approval, refusal, and every line he
speaks. Most mysteries end there.

## Milo isn't remembering this project
- Click **EchoMemory** on the bottom bar. If memory isn't on for this
  repository yet, the one-door card turns it on, connects your tools and
  offers the signposts, in one yes.

## My AI tool doesn't see the memory
- Run **EchoMemory: Connect Milo to your AI Tools**, then **restart the
  tool's session**: a tool reads its configuration when a session starts.
- Codex asks before it uses Milo's memory tools; say yes when it asks.

## A note is "missing"
- Check **your Inbox** first. A note an AI tool saves waits there for your
  Approve or Forget. That's the design, not a bug.
- A note marked *Keep this from the tools* is kept out of `team.md` and is
  never given to an AI, on purpose.

## Ask Milo found nothing
- Ask Milo matches the words in your notes, with no AI. Try the words the
  note itself would use, or open **Milo's Memory** and read.

## Memory arrived from a clone or a pull, and Milo ignores it
- Memory written somewhere else stays inert until you review and trust it.
  Milo asks once; "Not now" means he stays blind to it on purpose.

## Milo's talk answers are vague or he can't open his doors
- Milo thinks with your own Copilot in VS Code, or your own Ollama in other
  editors. Small local models are weaker at quoting and at opening doors;
  **Choose Milo's brain model** shows what you have and how big each is.

## "How much do I have left?" shows no Claude Code number
- Milo opens Claude Code's own panel, where **Account and Usage** shows the
  live numbers. He never estimates a Claude percentage.
- Codex's numbers come from its most recent session on this machine; if you
  haven't used Codex for a day, there may be none.

## Remote editors
- WSL, Remote-SSH, Dev Containers and Codespaces are not supported in this
  release. EchoMemory works on the machine the editor runs on.

## Still stuck
- Ask Milo: he answers basic EchoTools questions from a guide that ships
  with the extension, and offers Milo's office on echotools.dev for anything
  deeper.
- Or open an issue with the Output log, or email milo@echotools.dev.
