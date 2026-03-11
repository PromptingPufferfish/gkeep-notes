---
name: gkeep-notes
description: Google Keep notes via gkeepapi. List, search, create and manage notes. Add items to notes. User might also use the term "list" for a note.
homepage: https://github.com/PromptingPufferfish/gkeep-notes
metadata: {
  "openclaw": {
    "emoji":"📝",
    "requires": {"bins":["python3","gkeep"]}
  }
}
---

# gkeep

CLI wrapper for Google Keep using the unofficial gkeepapi.

## Commands

### General
gkeep.py is not a binary but a python source file. The binary is missing. As a workaround execute gkeep as follows:
```bash
python3 -m venv /home/administrator/.openclaw/workspace/skills/gkeep/venv
source /home/administrator/.openclaw/workspace/skills/gkeep/venv/bin/activate
python gkeep.py <args>
```

otherwise the command is
```bash
gkeep <args>
```

### Usage of gkeep command or gkeep.py

Before executing the first command, login with your Google account:
```bash
gkeep login <your.email.goes.here@gmail.com>
```
**Important:** Use an [App Password](https://myaccount.google.com/apppasswords), not your regular password. 2FA must be enabled.

List existing notes:
```bash
gkeep list
gkeep list --limit 10
```

Search for note:
```bash
gkeep search "shopping"
```

Get a specific note:
```bash
gkeep get <note_id>
```

Create a note:
```bash
gkeep create "Title" "Body text here"
```

Add item to an existing note:
```bash
gkeep add <note_id> <item>

Archive a note:
```bash
gkeep archive <note_id>
```

Delete a note (trash):
```bash
gkeep delete <note_id>
```

Pin a note:
```bash
gkeep pin <note_id>
```

Unpin a note:
```bash
gkeep unpin <note_id>
```

## Notes

- This uses an unofficial API that reverse-engineers Google Keep
- Could break if Google changes their internal API
- Token stored in $HOME/.openclaw/.config/gkeep/token.json
- First run bootstraps a local venv at $HOME/.openclaw/workspace/skills/gkeep-notes/.venv
- Active project with recent updates (as of Jan 2026)
