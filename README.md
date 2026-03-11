# 1. Install gkeep_notes skill

- For the moment:
```bash
git clone https://github.com/PromptingPufferfish/gkeep_notes $HOME/.openclaw/workspace/skills/gkeep_notes
```

- As soon as this skill is publishes on clawhub.ai:
```bash
clawhub install gkeep_notes
```

- After cloning from git/clawhub run in shell:
```bash
sudo apt install python3-pip
sudo apt install python3.12-venv
python3 -m venv $HOME/.openclaw/workspace/skills/gkeep_notes/venv
source $HOME/.openclaw/workspace/skills/gkeep_notes/venv/bin/activate
pip install -r requirements.txt
```

# 2. Setup OAuth Token Flow

OAuth Token Flow is the only authentication method which worked for me with a non-enterprise Google account.

## 2a. Manually create a token from the shell:
```bash
python3 -m venv $HOME/.openclaw/workspace/skills/gkeep_notes/venv
source $HOME/.openclaw/workspace/skills/gkeep_notes/venv/bin/activate
python $HOME/.openclaw/workspace/skills/gkeep_notes/generate_token.py 
```

- Enter your email, choose option 2 OAuth Token
- Open [https://accounts.google.com/EmbeddedSetup](https://accounts.google.com/EmbeddedSetup) in your browser -> Login -> I agree -> F12 (Developer Tools) -> Application -> Cookies -> copy&paste value of oauth_token
- token is generated -> copy the token between "=== RESULT ===" and "✅ TOKEN"

## 2b. Create token.json:
```bash
mkdir $HOME/.openclaw/.config/gkeep/
nano $HOME/.openclaw/.config/gkeep/token.json
```

- paste token into the file
- save with Ctrl+O and Enter, exit with Ctrl+X

# 3. New skill init & consistency check
```bash
openclaw gateway restart
```

Double check if skill appears as "ready" in the list:
```bash
openclaw skills list --eligible
```

