# Working Backwards Skill

A [Claude](https://claude.com/claude-code) Skill for writing Amazon-style **Working Backwards** documents — **PR/FAQs** (Press Release + Frequently Asked Questions).

The Working Backwards method starts with the customer and works backwards to the product. Instead of building something and then figuring out how to pitch it, you write the launch announcement *first* — forcing clarity on who the customer is, what problem you're solving, and why anyone should care, before a line of code is written. The output is a one-page press release plus a set of FAQs and an appendix.

This skill teaches Claude the full PR/FAQ structure, the narrative writing rules that make these documents work, and the quality bar to hold the output to.

---

## What it does

When active, the skill guides Claude to:

- Gather the essentials first — **who** the customer is, the **single** problem, the proposed solution, the launch date, and the key benefit.
- Write a **one-page press release** in customer language (no jargon, no implementation detail, no weasel words).
- Write **external and internal FAQs** — auto-numbered, ordered broad-to-specific, with trade-offs presented as options with pros and cons.
- Build an **appendix** — prioritised product backlog (P1–P4), KPIs with targets, and competitive analysis.
- Output as `.docx`, Markdown, or plain text.
- Hold the draft against a **quality checklist** before presenting it.

It triggers on phrases like *"Working Backwards"*, *"PR/FAQ"*, *"PRFAQ"*, *"press release and FAQ"*, and requests to write a product proposal, product requirements document, or feature definition in the Amazon narrative style — including partial requests like *"write me a press release for a new feature."*

## Contents

```
working-backwards/
├── SKILL.md                      # Entry point: workflow, voice/tone rules, quality checklist
└── references/
    ├── structure.md              # Full document template with worked examples
    └── writing-guide.md          # Narrative best practices, grammar, formatting standards
```

---

## Installation

This is a Claude Skill. Skills are folders containing a `SKILL.md` file; Claude loads them on demand when a task matches the skill's description. Pick whichever scope fits.

> **Note:** the skill folder is `working-backwards/` inside this repo. Install *that folder* (not the repo root) into your skills directory. The folder name becomes the skill name.

### Option A — Personal skill (available in every project)

Installs to your home directory so the skill is available across all your work.

```bash
git clone https://github.com/bigbenjoman/working-backwards-skill.git
mkdir -p ~/.claude/skills
cp -R working-backwards-skill/working-backwards ~/.claude/skills/
```

### Option B — Project skill (shared with your team via the repo)

Installs into a project so it's version-controlled and available to everyone who clones that project.

```bash
# from the root of your project
mkdir -p .claude/skills
git clone https://github.com/bigbenjoman/working-backwards-skill.git /tmp/wb-skill
cp -R /tmp/wb-skill/working-backwards .claude/skills/
```

Commit `.claude/skills/working-backwards/` and your teammates get the skill automatically.

### Option C — Claude.ai / Claude Desktop

Upload the skill as a `.zip` in **Settings → Capabilities → Skills**. Zip the `working-backwards` folder so the archive contains `working-backwards/SKILL.md` at its top level:

```bash
cd working-backwards-skill
zip -r working-backwards.zip working-backwards
```

### Verify it's installed

Open Claude Code and run:

```
/skills
```

You should see `working-backwards` in the list. Then just describe what you want — e.g. *"Write a PR/FAQ for a new feature that…"* — and Claude will load the skill automatically. You can also invoke it explicitly with `/working-backwards`.

---

## Best practices

Getting a strong PR/FAQ out of the skill depends as much on what you bring to it as on the skill itself.

**Come with a customer and a problem, not a solution.** The skill will ask *"who is the customer?"* and *"what is the single problem?"* first. Have specific answers — "parents of GCSE students in the UK," not "users." If you lead with the solution, the document will read backwards.

**One problem per document.** If your idea solves several distinct problems, write several PR/FAQs. Cramming multiple problems into one is the most common way these documents lose their edge. Use an umbrella PR/FAQ only to show how a suite of solutions serves one overarching problem.

**Bring data.** The skill replaces weasel words with numbers ("nearly all customers" → "7.6M customers"; "much faster" → "200ms to 30ms"). Give it real figures — market size, pricing, current baselines, research findings — or it can only draft placeholders for you to fill.

**Let it be uncomfortable.** A good problem statement should make you wince at how you treat customers today. Don't sand off the empathy; that discomfort is what creates the will to fix it.

**Treat the first draft as a draft.** At Amazon a PR/FAQ typically takes 2+ weeks to a first review and a month to approval. Iterate. Read `references/writing-guide.md` § The Review Process for how to run a silent-reading review meeting.

**Use the quality checklist as a gate, not a formality.** Before you circulate the document, walk the checklist at the end of `SKILL.md`. If it fails the *"so what?"* test — would a customer actually care? — the idea isn't ready, no matter how polished the prose.

**Keep implementation out of it.** "We'll use React and PostgreSQL" belongs nowhere in a PR/FAQ. Describe what the customer sees and does. Save the architecture for a separate technical plan.

---

## Learn more

- Colin Bryar & Bill Carr, *Working Backwards: Insights, Stories, and Secrets from Inside Amazon* — the canonical account of the method.
- [Anthropic Skills documentation](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) — how skills are structured and loaded.

## License

[MIT](./LICENSE)
