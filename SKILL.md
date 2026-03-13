---
name: gkeep-notes
description: Google Keep notes via gkeepapi. List, search, create and manage notes. Add items to notes. User might also use the term "list" for a note.
homepage: https://github.com/PromptingPufferfish/gkeep-notes
metadata: {
  "openclaw": {
    "emoji":"📝",
    "requires": {"bins":["python3"]}
  }
}
---

# gkeep

CLI wrapper for Google Keep using the unofficial gkeepapi.

## Commands

### General
gkeep.py is not a binary but a python source file. The binary is missing. As a workaround execute gkeep as follows:
```bash
python3 -m venv /home/administrator/.openclaw/workspace/skills/gkeep-notes/venv
source /home/administrator/.openclaw/workspace/skills/gkeep-notes/venv/bin/activate
python gkeep.py <args>
```

### Usage of gkeep.py command

Before executing the first command, login with your Google account. This login is only needed if token in $HOME/.openclaw/.config/gkeep/token.json does not exist:
```bash
gkeep.py login <your.email.goes.here@gmail.com>
```
**Important:** Use an [App Password](https://myaccount.google.com/apppasswords), not your regular password. 2FA must be enabled.

List existing notes:
```bash
gkeep.py list
gkeep.py list --limit 10
```

Search for note:
```bash
gkeep.py search "shopping"
```

Get a specific note:
```bash
gkeep.py get <note_id>
```

Create a note:
```bash
gkeep.py create "Title" "Body text here"
```

Add item to an existing note:
```bash
gkeep.py add <note_id> <item>

Archive a note:
```bash
gkeep.py archive <note_id>
```

Delete a note (trash):
```bash
gkeep.py delete <note_id>
```

Pin a note:
```bash
gkeep.py pin <note_id>
```

Unpin a note:
```bash
gkeep.py unpin <note_id>
```

## Notes

- This uses an unofficial API that reverse-engineers Google Keep
- Could break if Google changes their internal API
- First run bootstraps a local venv at $HOME/.openclaw/workspace/skills/gkeep-notes/.venv
- Active project with recent updates (as of Jan 2026)
