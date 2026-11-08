# Working Backwards Skill

> This skill is also part of [Product Skills](https://github.com/bigbenjoman/product-skills), a set of agent skills for finding, shaping, building and running products.

A [Claude](https://claude.com/claude-code) Skill for writing Amazon-style **Working Backwards** documents — **PR/FAQs** (Press Release + Frequently Asked Questions). Installs as a Claude Code plugin in two commands, or drop the skill folder in by hand.

The Working Backwards method starts with the customer and works backwards to the product. Instead of building something and then figuring out how to pitch it, you write the launch announcement *first* — forcing clarity on who the customer is, what problem you're solving, and why anyone should care, before a line of code is written. The output is a one-page press release plus a set of FAQs and an appendix.

This skill teaches Claude the full PR/FAQ structure, the narrative writing rules that make these documents work, and the quality bar to hold the output to.

---

## What it does

When active, the skill guides Claude to:

- Gather the essentials first — **who** the customer is, the **single** problem, the proposed solution, the launch date, and the key benefit.
- Write a **one-page press release** in customer language (no jargon, no implementation detail, no weasel words).
- Write **external and internal FAQs** — auto-numbered, ordered broad-to-specific, with trade-offs presented as options with pros and cons.
- Build an **appendix** — prioritised product backlog (P1–P4), KPIs with targets, market sizing, and competitive analysis.
- **Size the market bottoms-up** — TAM, SAM and SOM with filters and sources shown, rejecting top-down "we'll capture 1%" reasoning.
- **Analyse competitors honestly** — named rivals plus the status quo, compared on customer decision criteria, with a rule that you must lose at least one row to a *named competitor*.
- **Scale evidence to the document's stage** — hypothesis, validated or growth. The method never changes; what changes is how much evidence each figure must carry.
- **Reach a verdict, not just a description** — the analysis maps to a named outcome, including "market too small", "not differentiated" and "deprioritised with a trigger".
- Output as Markdown or plain text, and `.docx` where a docx skill is installed.
- Hold the draft against a **quality checklist** before presenting it.

It triggers on phrases like *"Working Backwards"*, *"PR/FAQ"*, *"PRFAQ"*, *"press release and FAQ"*, and requests to write a product proposal, product requirements document, or feature definition in the Amazon narrative style — including partial requests like *"write me a press release for a new feature."*

## Contents

```
.claude-plugin/
├── plugin.json                       # Plugin manifest
└── marketplace.json                  # Marketplace catalog (this repo is its own marketplace)
skills/
└── working-backwards/
    ├── SKILL.md                      # Entry point: workflow, voice/tone rules, quality checklist
    └── references/
        ├── structure.md              # Full document template with worked examples
        ├── writing-guide.md          # Narrative best practices, grammar, formatting standards
        └── market-and-competition.md # TAM/SAM/SOM sizing method and competitive analysis
```

It is markdown all the way down — **no binaries, no scripts, nothing to install alongside it**. If Claude ever tells you a CLI tool is required before it can write a PR/FAQ, that instruction came from somewhere else in your setup, not from this skill.

---

## Installation

This repo ships as a **Claude Code plugin** and doubles as its own plugin marketplace, so installing it is two commands. Copy-paste routes are kept below for Claude.ai and for anyone who'd rather not use plugins.

### Option A — Plugin (recommended)

In Claude Code:

```
/plugin marketplace add bigbenjoman/working-backwards-skill
/plugin install working-backwards@working-backwards-skill
```

Or from your shell:

```bash
claude plugin marketplace add bigbenjoman/working-backwards-skill
claude plugin install working-backwards@working-backwards-skill
```

The install command asks for a scope — **user** makes it available in every project, **project** commits it to the repo you're in, **local** keeps it to that one project without committing.

Updating later:

```
/plugin marketplace update working-backwards-skill
```

### Option B — Copy the skill folder in by hand

Skills are just folders containing a `SKILL.md`. Copy `skills/working-backwards/` into a skills directory and Claude will load it on demand.

```bash
# personal — available in every project
git clone https://github.com/bigbenjoman/working-backwards-skill.git
mkdir -p ~/.claude/skills
cp -R working-backwards-skill/skills/working-backwards ~/.claude/skills/
```

```bash
# project — version-controlled, shared with your team
# from the root of your project
mkdir -p .claude/skills
git clone https://github.com/bigbenjoman/working-backwards-skill.git /tmp/wb-skill
cp -R /tmp/wb-skill/skills/working-backwards .claude/skills/
```

Commit `.claude/skills/working-backwards/` and your teammates get the skill automatically.

### Option C — Claude.ai / Claude Desktop

Upload the skill as a `.zip` in **Settings → Capabilities → Skills**. Zip the skill folder so the archive contains `working-backwards/SKILL.md` at its top level:

```bash
cd working-backwards-skill/skills
zip -r ../working-backwards.zip working-backwards
```

### Verify it's installed

Open Claude Code and run:

```
/skills
```

You should see `working-backwards` in the list — as `working-backwards:working-backwards` if you installed the plugin, since plugin skills are namespaced by plugin name. Either way, just describe what you want — e.g. *"Write a PR/FAQ for a new feature that…"* — and Claude loads the skill automatically. `/plugin` shows the plugin's install state and lets you disable or remove it.

---

## Using it

Describe the work in your own words; the skill loads on the intent, not on a command.

```
Write a PR/FAQ for a scheduling tool aimed at duty managers
at multi-site care homes. We're pre-validation — no users yet.
```

It will ask for anything missing (customer, single problem, stage, launch date, company) before drafting, then produce the press release, FAQs and appendix in one pass.

Partial requests work too — you don't have to write the whole document:

```
Just the press release for this, one page.
Size the market for this idea bottoms-up.
Build the competitive matrix — we're up against Acme and Fooware.
```

To revise an existing document, point at the file rather than asking for a rewrite. The skill reads it, asks what to change, and edits surgically instead of regenerating over your work:

```
Revise prfaq.md — we've now done 12 customer interviews,
so move it to validated stage and update the sizing.
```

---

## Best practices

Getting a strong PR/FAQ out of the skill depends as much on what you bring to it as on the skill itself.

### Before you start

**Come with a customer and a problem, not a solution.** The skill will ask *"who is the customer?"* and *"what is the single problem?"* first. Have specific answers — "duty managers at multi-site care homes," not "users." If you lead with the solution, the document will read backwards.

**One problem per document.** If your idea solves several distinct problems, write several PR/FAQs. Cramming multiple problems into one is the most common way these documents lose their edge. Use an umbrella PR/FAQ only to show how a suite of solutions serves one overarching problem.

**Declare the stage, and declare it honestly.** The skill asks whether you are at **hypothesis** (no users, no interviews), **validated** (interviews or a pilot behind you) or **growth** (a live product with a funnel). This sets how much evidence every figure has to carry. Under-declaring is the easier abuse and the harder one to spot, because a thin hypothesis document is exactly what a reader expects — so the rule is now explicit: if the document draws on any interview, pilot or usage data anywhere, it is at least validated.

**Bring data.** The skill replaces weasel words with numbers ("nearly all customers" → "7.6M customers"; "much faster" → "200ms to 30ms"). Give it real figures — market size, pricing, current baselines, research findings — or it can only draft placeholders for you to fill.

### While drafting

**Decide the billing unit before any arithmetic.** Name the thing a single purchase covers — a seat, a site, a vehicle, a transaction, a household — and count that same thing in TAM, SAM and SOM. Counting companies and pricing per seat is the most common silent error in market sizing: both numbers are right and they describe different objects.

**Don't multiply correlated filters.** If you filter to larger firms and then apply a population-wide adoption rate, you have discounted company size twice. Source the joint condition, or apply the stronger filter alone and say so.

**Lose a row to a real competitor.** Every honest matrix has one. Conceding to the status quo doesn't count — doing nothing is free and already installed, so admitting it beats you costs you nothing and proves nothing.

**Keep implementation out — but not technical risk.** "We'll use React and PostgreSQL" belongs nowhere in a PR/FAQ; save the architecture for a technical plan. But *"we don't know whether this can be done inside 200ms, and that assumption carries the product"* is a disclosure, not a design decision, and the skill now asks for it. Name what might not be buildable and the spike that settles it — it is the cheapest thing to discover before a build decision rather than after.

**Say whether each customer is worth having.** A large SOM with negative per-customer economics is not a green light. The skill will not reach a "Go" verdict unless contribution margin is positive or lifetime value clears acquisition cost.

**Let it be uncomfortable.** A good problem statement should make you wince at how you treat customers today. Don't sand off the empathy; that discomfort is what creates the will to fix it.

### Before you circulate

**Expect a verdict, and expect it sometimes to be no.** The analysis maps to a named outcome — including *market too small*, *not differentiated*, *no switching trigger*, and *deprioritised with a named trigger condition and a review date*. If no combination of findings in your draft could have produced anything but "Go," the document was written to justify a decision already taken.

**Make the pre-mortem implicate you.** "A year from now this failed — what happened?" should name a failure your own design choices could cause. If the same sentence would fit any other company's document, it's a placeholder. Blaming the economy passes the checklist and teaches nobody anything.

**Know which quotes are fiction.** The customer testimonial in the press release is invented at *every* stage — it is a picture of the future, never evidence of demand, and it should never be challenged for lacking a source. The leader quote is the opposite: a real colleague will be asked to stand behind it, so it carries a real name or a bracketed placeholder, never an invented executive.

**Use the quality checklist as a gate, not a formality.** Before you circulate, walk the checklist at the end of `SKILL.md`. If it fails the *"so what?"* test — would a customer actually care? — the idea isn't ready, however polished the prose.

**Treat the first draft as a draft.** At Amazon a PR/FAQ typically takes 2+ weeks to a first review and a month to approval. Iterate: point the skill at the existing file and it revises in place rather than regenerating over your edits. See `skills/working-backwards/references/writing-guide.md` § The Review Process for how to run a silent-reading review meeting.

---

## Learn more

- Colin Bryar & Bill Carr, *Working Backwards: Insights, Stories, and Secrets from Inside Amazon* — the canonical account of the method.
- [Anthropic Skills documentation](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) — how skills are structured and loaded.

## License

[MIT](./LICENSE)
