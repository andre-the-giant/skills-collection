# skills-collection

A personal library of Claude Code skills, version-controlled in Git and available on every machine through two symlinks. Each skill extends Claude Code with specialized knowledge, workflows, or audit capabilities.

## Skills

### accessibility

Audits and improves web accessibility following Web Content Accessibility Guidelines (WCAG) 2.2. Apply it when you need an accessibility audit, want to verify WCAG compliance, or need to add screen reader support and keyboard navigation to a page.

**Trigger phrases:** "improve accessibility", "a11y audit", "WCAG compliance", "screen reader support", "keyboard navigation", "make accessible"

---

### find-skills

Helps you discover and install skills from the open agent skills ecosystem. Use it when you ask "how do I do X", want to know if a skill exists for a task, or want to extend Claude Code with new capabilities.

**Trigger phrases:** "find a skill for X", "is there a skill that can...", "how do I do X"

---

### fixing-accessibility

Audits and fixes Hypertext Markup Language (HTML) accessibility issues at the code level. It targets ARIA labels, keyboard navigation, focus management, color contrast, and form error handling. Run it on a specific file or activate it at the start of a conversation to apply its constraints to all UI work.

**Trigger phrases:** adding interactive controls, forms, dialogs, reviewing WCAG compliance

---

### seo-aeo-best-practices

Applies Search Engine Optimization (SEO) and Answer Engine Optimization (AEO) best practices. Covers metadata, Open Graph tags, sitemaps, `robots.txt`, hreflang, JSON-LD structured data, Experience, Expertise, Authoritativeness, and Trustworthiness (EEAT) principles, and content optimized for AI answer surfaces like ChatGPT and Perplexity.

**Trigger phrases:** implementing page SEO, technical SEO, schema markup, international SEO, AI-overview readiness

---

### skill-creator

Creates new skills, modifies existing ones, and measures skill performance. It walks you through drafting a skill, generating test prompts, running evaluations, reviewing results, and iterating until the skill performs well. It also optimizes a skill's description so Claude Code triggers it accurately.

**Trigger phrases:** "create a skill", "improve an existing skill", "run evals", "benchmark skill performance", "optimize skill description"

---

### vercel-react-best-practices

Applies React and Next.js performance optimization guidelines from Vercel Engineering. Contains 70 rules across eight categories, prioritized by impact. Use it when writing, reviewing, or refactoring React components, Next.js pages, data fetching logic, or bundle configuration.

**Trigger phrases:** React components, Next.js pages, data fetching, bundle optimization, performance improvements

---

### writing-guidelines

Reviews documentation and prose against Vercel writing standards. Checks voice, tone, sentence length, prohibited filler words, code block formatting, and list structure. It fetches the latest rules from the source repository before each review, so it always applies the current guidelines.

**Trigger phrases:** "review my docs", "check writing style", "audit prose", "review docs voice and tone"

---

## Setup

### First-time setup on a new machine

Clone the repository and create both symlinks:

```bash
git clone https://github.com/andre-the-giant/skills-collection.git ~/src/skills-collection

rm -rf ~/.claude/skills
ln -s ~/src/skills-collection ~/.claude/skills

mkdir -p ~/.agents
rm -rf ~/.agents/skills
ln -s ~/src/skills-collection ~/.agents/skills
```

The first symlink makes skills available to the Claude Code CLI. The second makes them available to `npx skills`.

### Add a skill with npx (recommended)

```bash
npx skills add https://github.com/some-author/some-repo --skill skill-name

cd ~/src/skills-collection && git add . && git commit -m "add skill-name" && git push
```

### Add a skill manually

```bash
mkdir ~/src/skills-collection/my-skill-name
# Add a SKILL.md file inside the new directory

cd ~/src/skills-collection && git add . && git commit -m "add my-skill-name" && git push
```

### Sync on an existing machine

```bash
cd ~/src/skills-collection && git pull
```

Once pulled, the symlinks pick up the new skills immediately. No restart required.
