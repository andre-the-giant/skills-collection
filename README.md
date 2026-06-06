# skills-collection

My personal Claude Code skills, synced across machines via Git.

## How it works

Two symlinks point to this repo:
- `~/.claude/skills/` → used by Claude Code CLI
- `~/.agents/skills/` → used by `npx skills`

Any skill added here (manually or via `npx skills add`) is available immediately and syncs to all machines via `git push` / `git pull`.

## First-time setup on a new machine

```bash
# 1. Clone the repo
git clone https://github.com/andre-the-giant/skills-collection.git ~/src/skills-collection

# 2. Create both symlinks
rm -rf ~/.claude/skills
ln -s ~/src/skills-collection ~/.claude/skills

rm -rf ~/.agents/skills
mkdir -p ~/.agents
ln -s ~/src/skills-collection ~/.agents/skills
```

## Adding a skill via npx (recommended)

```bash
npx skills add https://github.com/some-author/some-repo --skill skill-name

# Then commit and push
cd ~/src/skills-collection && git add . && git commit -m "add skill-name" && git push
```

## Adding a skill manually

```bash
mkdir ~/src/skills-collection/my-skill-name
# drop a SKILL.md inside...

cd ~/src/skills-collection && git add . && git commit -m "add my-skill-name" && git push
```

## Syncing on an existing machine

```bash
cd ~/src/skills-collection && git pull
```
