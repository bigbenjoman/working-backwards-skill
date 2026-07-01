---
name: working-backwards
description: "Write Amazon-style Working Backwards documents (PR/FAQs). Use this skill whenever the user mentions 'Working Backwards', 'PR/FAQ', 'PRFAQ', 'press release and FAQ', 'product definition document', or asks to write a product proposal, product requirements document, or feature definition in the Amazon narrative style. Also trigger when editing, reviewing, or providing feedback on an existing PR/FAQ. This skill covers the full PR/FAQ structure: press release, external FAQs, internal FAQs, appendix, and product backlog. It can output as .docx (using the docx skill), markdown, or plain text. Always use this skill even for partial requests like 'write me a press release for a new feature' or 'help me with the FAQ section of my PR/FAQ'."
---

# Working Backwards Document (PR/FAQ) Skill

## What This Skill Does

Generates Amazon-style Working Backwards documents — the methodology that starts with the customer and works backwards. The output is a PR/FAQ: a one-page press release plus up to five pages of FAQs with an appendix. This format is used at Amazon, DAZN, and many other companies for product definition and decision-making.

**Before writing anything**, read `references/structure.md` for the full document template and `references/writing-guide.md` for narrative writing best practices.

## When to Use

- Creating a new PR/FAQ from scratch
- Drafting just the press release section
- Writing external (customer) or internal (stakeholder) FAQs
- Building the appendix (backlog, KPIs, competitive analysis)
- Reviewing or improving an existing PR/FAQ
- Converting a product idea into Working Backwards format

## Workflow

### Step 1: Gather Context

Before writing, establish these essentials. Ask the user if not provided:

1. **Who is the customer?** Be specific — not "users" but "parents of GCSE students in the UK" or "enterprise procurement managers"
2. **What is the single problem or opportunity?** There can only be one. If there are multiple, split into separate PR/FAQs
3. **What is the proposed solution?** High-level — no implementation details
4. **What is the launch date?** Real or aspirational
5. **What is the key customer benefit?** The one thing that matters most
6. **What company is this for?** Needed for confidentiality footer and leader quote

### Step 2: Write the Press Release (1 page)

Read `references/structure.md` § Press Release Template for the exact structure.

Key rules:
- **One page maximum.** If it needs more, the idea isn't clear enough
- **Customer language only.** No internal jargon, no technical implementation
- **Eliminate weasel words.** "Nearly all customers" → "7.6M customers". "Huge improvement" → "+25 basis points"
- **Replace adjectives with data.** "Much faster" → "Reduced latency from 200ms to 30ms"
- **Under 30 words per sentence.** "Due to the fact that" → "because"
- **Pass the "so what" test.** Would a customer actually care about this?
- **Information hierarchy.** Assume the reader stops at any point — every sentence adds the next most important thing
- **Make the reader empathise with the problem.** Reading it should make us question why we do this to customers
- **The solution can't be magic.** You need at least a high-level idea of the entire solution

### Step 3: Write the FAQs (2-5 pages)

This is where the core product definition happens. Two sections:

**External (Customer) FAQs** — Questions a customer would ask:
- What is this? How does it work?
- How do I find/access it?
- What does it cost?
- What do I need to use it?
- What's different from alternatives?

**Internal (Stakeholder) FAQs** — Questions leadership and teams would ask:
- What are the trade-offs and why?
- What data supports this approach?
- What are the risks and mitigations?
- What's the competitive positioning?
- What's the estimated ROI?
- What metrics define success?
- What options were considered?

Rules for FAQs:
- **Order by breadth then importance.** Start broad, narrow to specific
- **Auto-number all FAQs.** Use sequential numbering across both sections
- **Answer every question a reader might ask.** The ideal PR/FAQ eliminates the need for discussion
- **Present options with pros/cons.** Don't just state a decision — show the alternatives considered
- **Use data to support decisions.** Include market data, customer research, projections
- **Use "we" in internal FAQs.** Customer voice in external, company voice in internal
- **No implementation details.** Describe the customer experience, not how it's built

### Step 4: Write the Appendix

Include as relevant:
- **Product Backlog** — Prioritised requirements with P1/P2/P3/P4 ratings (see `references/structure.md` § Priority Definitions)
- **KPIs** — Success metrics with specific targets
- **Competitive Analysis** — Competitor experiences and benchmarking
- **Visuals** — Wireframes, user flows, UX mocks (reference only in text)
- **Supporting Data** — Market research, customer data, financial projections
- **GTM Tags** — Metrics for measuring feature usage

### Step 5: Format and Output

**If outputting as .docx:** Use the docx skill. Apply these formatting rules:
- Paper: A4
- Margins: Narrow (0.5cm left/right, 0.5cm top/bottom) — in DXA: 284 left/right, 284 top/bottom
- Font: Arial, minimum 10pt, single line spacing
- Footer: "[Company Name] Confidential" centred, page number right-aligned
- FAQs must be auto-numbered
- Headings: Bold, consistent hierarchy

**If outputting as markdown or text:** Follow the same structural template but use markdown formatting.

## Voice and Tone Rules

| Section | Voice | Perspective |
|---------|-------|-------------|
| Headline & Sub-heading | Customer-facing, compelling | Third person |
| Press Release body | Customer-centric, simple language | Third person |
| Leader Quote | Visionary but specific | First person (quoted) |
| Customer Testimonial | Specific, believable, human | First person (quoted) |
| External FAQs | Customer language, helpful | Second person ("you") |
| Internal FAQs | Business language, analytical | First person plural ("we") |
| Appendix | Data-driven, precise | Neutral/analytical |

## Quality Checklist

Before presenting the document, verify:

- [ ] Press release is one page or fewer
- [ ] Single clear problem or opportunity stated
- [ ] Customer is explicitly defined
- [ ] No weasel words (nearly, significant, many, often, huge)
- [ ] Adjectives replaced with data where possible
- [ ] Sentences under 30 words
- [ ] No implementation details in press release or external FAQs
- [ ] FAQs are auto-numbered sequentially
- [ ] Options presented with pros and cons in internal FAQs
- [ ] Priority definitions included with backlog
- [ ] Confidentiality footer included
- [ ] Passes the "so what" test — a customer would care about this
- [ ] Leader quote captures the single most important customer value
- [ ] Customer testimonial is specific, believable, and human-sounding

## Common Mistakes to Avoid

1. **Starting with the solution, not the customer.** Always begin: who is the customer and what is their problem?
2. **Multiple problems in one PR/FAQ.** One problem = one PR/FAQ. Write an umbrella PR/FAQ if needed
3. **Vague language.** "Improved experience" means nothing. Quantify everything
4. **Internal jargon in customer-facing sections.** If your customer wouldn't say it, rewrite it
5. **Missing trade-off analysis.** Every decision had alternatives — show them
6. **No data.** Assertions without evidence are opinions. Back claims with research, metrics, or projections
7. **Too long.** Press release > 1 page = unclear thinking. Total document > 6 pages (excl. appendix) = too much
8. **Implementation details.** "We'll use React and PostgreSQL" doesn't belong anywhere in a PR/FAQ. Describe what the customer sees and does
9. **Sensitive information.** No customer PII, security details, or credentials

## Reference Files

- `references/structure.md` — Full document template with all sections and examples
- `references/writing-guide.md` — Narrative writing best practices, grammar rules, formatting standards
