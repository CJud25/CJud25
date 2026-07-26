## Hi there 👋

**I work in AbilityOne compliance, and I kept watching people make expensive decisions off numbers that
don't mean what the label says. So I built the tools I wished existed.**

Operations Analyst / BI + Automation. I work the whole path — public data → validated model → a screen a
decision-maker can act on. The part I've gotten good at is the boundary: what's a fact, what's an
estimate, and what a tool should **refuse to compute** rather than guess.

Each project below names the thing it won't do.

---

## 🛰️ GovCon Recompete Radar
*Which expiring DoD cyber/IT contracts are worth pursuing — and which numbers you can defend.*

An ETL + BI pipeline over public **USAspending.gov / SAM.gov** data that finds expiring DoD cyber/IT
contracts, scores each for pursuit fit, and **quarantines the records it can't stand behind** instead of
dressing them up as leads. Ships a DuckDB SQL pack, a Power BI star schema, and a Streamlit app that
imports the same scoring library the pipeline runs — one source of truth, no mirrored scorers.

> **What it refuses:** I never published a recall figure for the link engine, because only about **4% of
> candidates** match a live solicitation — the set I miss is structurally unobservable, so any recall
> number would be fiction. When a recency filter cut established links from **4,163 to 1,311**, I
> shipped the smaller number. The app also declines to estimate a competitive price range below a
> comparables floor.

[![GovCon Recompete Radar — the Monday briefing](https://raw.githubusercontent.com/CJud25/GovConRadar/main/docs/screenshots/home_demo.png?v=2026-07-26)](https://govconradar.streamlit.app)

**[Live app](https://govconradar.streamlit.app)** · **[Repo](https://github.com/CJud25/GovConRadar)** · **[Scoring methodology](https://github.com/CJud25/GovConRadar/blob/main/docs/scoring_methodology.md)**

---

## 🐾 Rescue Ops Workbook
*The one other people actually use.*

A five-module Google Apps Script package running the intake and volunteer-coordination workflow for a
small dog-rescue nonprofit. Installed on their live workbook, in use by their coordinators. The Contact
Log doubles as new-applicant intake, so the record and the follow-up stay in one place instead of two.

> **What it taught me:** two bugs only appeared once real people used it — a timezone mismatch on the
> sheet and a phantom-row append — and both were found *after* install, not before. Nothing in a test
> fixture would have surfaced them. Every other project on this page has a user count of one; this one
> doesn't, and that difference has been the most useful thing in my portfolio to think about.

*Not public — it runs on a real organization's data.*

---

## 🛡️ CMMC Vault
*The compliance number that looks like a finish line but isn't.*

A session-only tool that scores a **NIST SP 800-171 Rev 2 / CMMC Level 2** self-assessment the way the
DoD does, and makes one missed truth impossible to ignore: **88 is necessary but not sufficient**. The
sample org scores **89 and is still not conditionally ready**, because four open requirements can't be
deferred to a POA&M. The tool turns that gap into an ordered remediation plan.

> **What it refuses:** it can never claim to confer CMMC status — a machine-enforced language contract
> in CI blocks the vocabulary. A CMMC Status is conferred only by an assessment recorded in SPRS; this
> is a readiness self-estimate, and it says so on every surface.

[![CMMC Vault — sample org at 89, "Not conditionally ready"](https://raw.githubusercontent.com/CJud25/CMMCVault/main/docs/img/live-demo-sample-89.png)](https://cmmcvault-demo.streamlit.app/)

**[Live app](https://cmmcvault-demo.streamlit.app/)** · **[Repo](https://github.com/CJud25/CMMCVault)** · **[Language contract](https://github.com/CJud25/CMMCVault/blob/main/docs/language-contract.md)** · **[Case study](https://github.com/CJud25/CMMCVault/blob/main/docs/case-study.md)**

---

## 🧮 FMP Calculator
*A fair-market-price band for AbilityOne services and products, with every number cited.*

Mirrors the Commission's official cost buildup (Policy 51.601) line by line — labor, fringe, burden,
overhead, G&A, net proceeds, program fee — and cites the authority for each rate rather than asserting
it. Produces a **recommended price band, never "the" FMP**; the Commission has sole authority to
determine that.

> **What it refuses:** it will not price a scenario whose indirect rates were never entered. No
> headline, no metric, no export. An unset rate and a deliberate zero are different things, and
> treating a blank field as 0% silently understated a real buildup by millions — so now blank means
> *stop*, not *zero*.

**[Live app](https://fmp-calculator.streamlit.app)** · **[Repo](https://github.com/CJud25/FMP-Calculator)**

---

Also public: **[ReconRadar](https://github.com/CJud25/ReconRadar)** (a cited, score-free opportunity
evidence packet — I built a feasibility × confidence × urgency score and then deleted it, because a
score laundered screened candidates into something that looked retrieved) ·
**[ROCC](https://github.com/CJud25/ROCC)** (recruiting and outreach signal on synthetic data — it scores
sources and contracts, never people) ·
**[OpsPilot Command Center](https://github.com/CJud25/OpsCommandCenter)** (ranks what to automate across
two unrelated operations on one scale).

---

*On authorship: I specify, decompose and verify; a model writes most of the line-level code. What's mine
is the specification, the slice boundaries, the decision to run an adversarial review pass at all, and
the calls about what to refuse to compute or delete. Each repo's README carries a
`## How this was built` section, and it credits the review passes with the finds rather than me.*
