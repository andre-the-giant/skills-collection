# skills-collection

My personal Claude Code skills, synced across machines via Git.

## How it works

`~/.claude/skills/` is a symlink pointing to this repo at `~/src/skills-collection`.
Any skill added here is available to Claude Code immediately, and syncs to all machines via `git push` / `git pull`.

## First-time setup on a new machine

```bash
# 1. Clone the repo
git clone https://github.com/andre-the-giant/skills-collection.git ~/src/skills-collection

# 2. Create the symlink
ln -s ~/src/skills-collection ~/.claude/skills
```

> If `~/.claude/skills` already exists on the machine, remove it first:
> ```bash
> rm -rf ~/.claude/skills
> ```

## Adding a new skill

```bash
# Create a folder with a SKILL.md inside
mkdir ~/src/skills-collection/my-skill-name
# ... add your SKILL.md ...

# Push to sync to all machines
cd ~/src/skills-collection && git add . && git commit -m "add my-skill-name" && git push
```

## Syncing on an existing machine

```bash
cd ~/src/skills-collection && git pull
```
