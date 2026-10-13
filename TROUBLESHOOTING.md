# EchoMemory: Troubleshooting

First stop, always: **View > Output > pick "EchoMemory"** in the dropdown.
Milo narrates every note saved, every approval, every answer and every line
he speaks. Most mysteries end there.

## Milo isn't remembering this project
- Click **EchoMemory** on the bottom bar. If memory isn't on for this
  project yet, one click turns it on and creates `.milo/`.
- EchoMemory needs EchoAvatar and EchoVoice. If either is missing or
  disabled, install or enable it, then **Reload Window**.

## A note is "missing"
- Check **your Inbox** first. A note Milo writes for you (one he condensed,
  or a summary of one of your notes) waits there for your Approve or Forget.
  That's the design, not a bug.
- Editing `notes.md` by hand changes nothing Milo remembers: the page is
  printed from his records. Use **Pin & Note**, or ask Milo.

## Ask Milo found nothing
- Ask Milo matches the words in your notes, with no AI. Try the words the
  note itself would use, or open **What Does Milo Remember?** and read.

## Notes arrived with a project, and Milo ignores them
- Notes written somewhere else stay inert until you review and trust them.
  Milo asks once; "Not now" means he stays blind to them on purpose.

## Milo's talk answers are vague, or he can't open his doors
- Milo thinks with your own Copilot in VS Code, or your own Ollama in other
  editors. Small local models are weaker at quoting and at opening doors;
  **Choose Milo's brain model** shows what you have and how big each is.
- A brain setting in a project's `.vscode/settings.json` is ignored on
  purpose: set it in your own user settings.

## "How much do I have left?" shows no Claude Code number
- Milo opens Claude Code's own panel, where **Account and Usage** shows the
  live numbers. He never estimates a Claude percentage.
- Codex's numbers come from its most recent session on this machine; if you
  haven't used Codex for a day, there may be none.

## "The two can't run together"
- That message means a second EchoMemory build is installed in the same
  editor. Uninstall one, then **Reload Window**.

## Remote editors
- WSL, Remote-SSH, Dev Containers and Codespaces are not supported in this
  release. EchoMemory works on the machine the editor runs on.

## Still stuck
- Ask Milo: he answers basic EchoTools questions from a guide that ships
  with the extension, and offers Milo's office for anything deeper.
- Or open an issue with the Output log, or email milo@echotools.dev.
