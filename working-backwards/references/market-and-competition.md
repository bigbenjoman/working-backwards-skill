# Market Sizing and Competitive Analysis Reference

How to size the opportunity (TAM/SAM/SOM) and position against alternatives. Both belong in the internal FAQs, with workings in the appendix. **Neither belongs in the press release** — a customer does not care how big the market is.

---

## Part 1: Market Sizing (TAM, SAM, SOM)

### The Three Numbers

| Term | Definition | The question it answers |
|------|------------|------------------------|
| **TAM** — Total Addressable Market | Total annual revenue if every customer with this problem bought a solution, with no constraints on geography, business model, or competition | "How big is this category?" |
| **SAM** — Serviceable Addressable Market | The share of TAM you could actually sell to, given your business model, geography, channel, language, platform and segment | "How big is the part we can reach?" |
| **SOM** — Serviceable Obtainable Market | The share of SAM you can realistically win within the plan horizon, given competition, capacity and go-to-market | "How much will we actually get?" |

Each number is a filtered subset of the one above it: **TAM → SAM → SOM**. If your document states only one of the three, it is marketing, not analysis.

### The Only Acceptable Method: Bottoms-Up

Build every number from countable units:

```
Market size = (number of qualifying customers) × (annual revenue per customer)
```

Both terms need a source. If either is a guess, mark it `[CITATION NEEDED]` and say so.

**Top-down sizing is not acceptable** in a PR/FAQ. Top-down means starting with a large published figure and applying a capture percentage:

| Rejected | Why |
|----------|-----|
| "The global e-learning market is $250B. If we capture 1%, that's $2.5B." | 1% is not a plan. Nothing in the sentence is falsifiable |
| "The UK tutoring market is worth £2B and growing 12% annually." | This is category trivia, not *your* addressable revenue |
| "There are 32M SMEs in Europe." | Not all have the problem, not all can buy from you |

The tell is a percentage that appears with no justification. **A capture percentage is an output of your analysis, never an input to it.**

### Worked Example

Every figure below is **illustrative** — replace with sourced numbers. The point is the structure, and that each line shows its arithmetic and its filter.

**Product:** £7.99/month revision app for UK GCSE students.

**TAM — everyone in the category**
```
UK pupils in Years 10–11                      2,000,000   [source: DfE school census, YYYY]
× annual subscription (£7.99 × 12)            £95.88
TAM                                           £191.8M/year
```
*Meaning: every GCSE household in the UK subscribing. Not achievable — a ceiling, not a target.*

**SAM — the part we can reach**
```
TAM                                           £191.8M
× households that pay for academic support     27%      [source: Sutton Trust tutoring survey, YYYY]
× households with suitable device + broadband  94%      [source: Ofcom Technology Tracker, YYYY]
SAM                                           £48.7M/year
```
*Each filter is a real constraint of the business model, with a source. "Would consider paying" is not a filter — willingness must be evidenced, not assumed.*

**SOM — what we will actually win**
```
SAM                                           £48.7M
× realistic year-1 share                       1.5%
SOM (year 1)                                  £730K/year
≈ 7,600 subscribers
```
*The 1.5% must be defended, not asserted. See below.*

### Defending the SOM Percentage

SOM is where documents lose credibility. Rules:

1. **State the implied share explicitly.** Write "1.5% of SAM" next to the number. Hiding it inside a revenue figure is evasion.
2. **Justify it with a comparable, not a hope.** "Competitor X reached 4% of this SAM in 18 months with a paid-acquisition model we can match" is a defence. "We think 5% is conservative" is not.
3. **Anything above 10% of SAM in year one requires a named structural reason** — an existing distribution channel, an installed base, an exclusive partnership, a regulatory position. Without one, it is fantasy. Most new entrants without a distribution advantage land between 0.1% and 2%.
4. **Reconcile SOM with your KPIs.** If SOM implies 7,600 subscribers and the appendix KPI target says 1,000, one of them is wrong. This mismatch is the single most common defect. Check it before circulating.
5. **Reconcile SOM with capacity.** If SOM implies 7,600 customers and support can handle 500, the number is not obtainable.

### Signals of Weak Market Sizing

Check the draft for these. Each one is a review comment waiting to happen:

- A capture percentage used as an input ("if we get just 2%…")
- TAM quoted with no SAM or SOM
- No source for the population count, or a source with no year
- Price assumed rather than tested — no pricing research, no willingness-to-pay evidence
- SAM equal or nearly equal to TAM (means no real filters were applied — almost always wrong)
- SOM presented as a range so wide it commits to nothing ("£500K–£15M")
- Market size grows between document drafts with no new evidence
- Revenue confused with market size (yours is revenue; the market is everyone's)
- The same customer counted in two segments and summed
- Growth rates applied to make a small market look big ("only £4M today, but growing 40% annually") without stating when it becomes large enough to matter

### When Market Sizing Is Not the Right Frame

Do not force TAM/SAM/SOM onto:

- **Internal tools** — size by hours saved × loaded cost, or by cost avoided
- **Platform and infrastructure work** — size by the products it unblocks
- **Defensive features** — size by revenue retained or churn prevented; state the churn baseline
- **Free or open-source offerings** — size by adoption and the strategic asset created, and say explicitly what the monetisation path is (or that there isn't one)

In each case, replace the section with the appropriate measure rather than omitting sizing altogether. Say which frame you are using and why.

---

## Part 2: Competitive Analysis

### Name Real Competitors

Never write "other solutions in the market" or "various competitors". Name them. If you cannot name three, either the analysis is not done or the market does not exist — both are findings worth surfacing.

**Always include the status quo.** The most common competitor is not a company; it is the spreadsheet, the WhatsApp group, the agency, the intern, or doing nothing. If customers currently solve this some other way, that way is your primary competitor, and it is free and already installed. A competitive matrix without a "do nothing / today" column is incomplete.

### The Comparison Matrix

Replace feature checkboxes with **customer decision criteria** — the dimensions on which a customer actually chooses. Include the status quo, and mark who wins each row.

```
| Dimension (customer decision criterion) | Us | Competitor A | Competitor B | Status quo (today) | Advantage |
|---|---|---|---|---|---|
| [e.g. Time to first value] | 5 min | 2 days | 30 min | Immediate | Competitor B |
| [e.g. Cost per pupil per year] | £96 | £340 | £180 | £0 | Us |
| [e.g. Curriculum coverage] | 4 subjects | 12 subjects | 9 subjects | Unlimited | Competitor A |
| [e.g. Parent visibility] | Weekly report | None | None | Direct | Us |
```

Rules for the matrix:

1. **Dimensions are customer criteria, not features.** "SSO support" is a feature. "Time to first value" is a criterion. If a customer would not weigh it when choosing, cut the row.
2. **You must lose at least one row.** A matrix where you win every dimension is evidence of confirmation bias, not superiority. If you genuinely win everything, your dimensions are self-serving — you have chosen the rows you win. Find the rows where a competitor is better and include them.
3. **Date-stamp the analysis.** Competitor facts decay. Add "as at [Month YYYY]" beneath the table and cite where each claim came from.
4. **Describe competitors fairly.** Words like "merely", "just", "only" and "simply" applied to a competitor's product signal that the analysis is a pitch. Strip them.
5. **No unverifiable claims about competitors.** Their pricing, features and positioning must be observable from public sources. Do not assert their roadmap, margins or internal problems.

### The 90-Day Response Test

For each named competitor, answer:

> "If they read our press release tomorrow morning, what would they do in the next 90 days — and where would that leave us?"

If the honest answer is "copy it within a quarter", the differentiation is insufficient and the document should say so. This test converts a static matrix into a strategic argument, and it is the fastest way to find out whether you have a product or a feature.

### Feature Advantage vs Structural Advantage

State which kind of advantage you have. They are not equivalent.

| Type | Examples | Durability |
|------|----------|-----------|
| **Feature advantage** | A capability they lack, better UX, faster performance, lower price | Closes in months. Assume it is temporary |
| **Structural advantage** | Proprietary data, network effects, distribution/installed base, cost structure, switching costs, regulatory position, exclusive supply | Persists — this is what makes the position defensible |

A PR/FAQ whose entire differentiation is a feature list has not answered "why won't the incumbent just build this?" Answer it explicitly. If the only answer is "we'll move faster", say that plainly and let the reader weigh it — an honest weak answer is better than a disguised one.

### Signals of Weak Competitive Analysis

- No competitor named, or fewer than three
- No status quo / do-nothing column
- We win every row
- Competitors described dismissively
- The analysis is undated, or cites no sources
- Differentiation is entirely feature-based, with no structural advantage stated
- "We have no competitors" — this means the market is unproven, the analysis is incomplete, or the customer solves the problem another way and you have not identified it. Never a strength
- The competitive FAQ answers "what makes us different?" without answering "why can't they copy it?"

---

## Where This Material Goes in the Document

| Content | Location |
|---------|----------|
| Headline market opportunity (one sentence, SOM only) | Internal FAQ — "How big is the opportunity?" |
| TAM/SAM/SOM with filters and sources | Appendix — Market Sizing |
| Named competitors and positioning | Internal FAQ — "What is the competitive positioning?" |
| Full comparison matrix | Appendix — Competitive Analysis |
| Why competitors cannot easily copy us | Internal FAQ — "What are our unique points of difference?" |
| Anything at all about market size | **Never in the press release or external FAQs** |
