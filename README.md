## Hi there 👋

**I build automation solutions that stick.** My approach is straightforward: understand the bottleneck, 
design a solution that fits the workflow, ship it, and make sure it actually works in production. I work 
the full path—from initial discovery through deployment and handoff—because half-baked automation creates 
more problems than it solves. Whether it’s compliance workflows, HR systems, data pipelines, or operational 
dashboards, I focus on creating tools that reduce friction and let teams do what they actually want to do.

My toolkit spans Power Platform (Automate, Apps, BI), Python, Streamlit, and modern data tools—skills 
I’ve built independently while working in Compliance, navigating Oracle HR systems and complex regulatory 
workflows. I hold an Azure AI Engineer Associate certification and multiple other Anthropic certifications 
and Microsoft credentials. I’ve created and shipped off solutions ranging from disability eligibility 
automation and grant-writing dashboards to service-desk optimization engines and compliance documentation 
systems. I also maintain a freelance practice on Upwork focused on Power Platform development.


---

# 🧭 TENS HQ

Federal contract capture is one long workflow with six distinct jobs in it. You find the expiring contract,
you investigate who holds it, you price the work, you prove you're compliant, you staff it, and — if you're
honest — you go back later and check whether your call was any good.

Most tools pick one of those and pretend the others don't exist. **TENS HQ is that whole lifecycle**, built
as six separate applications that hand each other typed JSON rather than one application with six tabs.

That was a deliberate architectural call, not an accident of how it grew. A single app would mean one trust
boundary around six very different kinds of data — public award records, an organization's internal indirect
rates, and applicant information that must never be scored. Keeping them apart keeps the blast radius small
and lets each one state its own governance rules honestly. The seams are the point:
[`contracts/`](https://github.com/CJud25/TENS-HQ/tree/main/contracts) holds the two versioned handoffs
(`radar-handoff/v1`, `packet-fmp/v1`) that let the stages talk without sharing a database.

| Stage | Module | What it does | |
|---|---|---|---|
| **Find** | GovCon Recompete Radar | Surfaces expiring DoD cyber/IT contracts from USAspending and SAM.gov with defensible forward signals — and quarantines the records it can't stand behind | [app](https://govconradar.streamlit.app) · [repo](https://github.com/CJud25/GovConRadar) |
| **Investigate** | ReconRadar | Builds a cited, provenance-tracked evidence packet per opportunity. Score-free by design — a human decides | [app](https://reconradar.streamlit.app) · [repo](https://github.com/CJud25/ReconRadar) |
| **Price** | FMP Calculator | A low/med/high fair-market-price band mirroring Commission Policy 51.601 line by line, every rate cited | [app](https://fmp-calculator.streamlit.app) · [repo](https://github.com/CJud25/FMP-Calculator) |
| **Comply** | CMMC Vault | Scores CMMC Level 2 readiness against NIST SP 800-171 — because a high control count is not the same as ready | [app](https://cmmcvault-demo.streamlit.app) · [repo](https://github.com/CJud25/CMMCVault) |
| **Staff** | ROCC | Aggregates recruiting and outreach signal by source and contract, on synthetic data. Scores sources and contracts, never people | [app](https://controlcenter.streamlit.app) · [repo](https://github.com/CJud25/ROCC) |
| **Learn** | EDGE | Logs every pursue/pass call and the analyst's decision-time confidence so judgment can be calibrated later | *no app — by design* |

**EDGE has no application and that's the interesting part.** Calibration needs a corpus of real decisions
with known outcomes. I don't have one yet, so the logging kit is built and the calibration read is
specified and deliberately unbuilt. Shipping a reliability curve over four decisions would look like
analytics and function as noise.

[![GovCon Recompete Radar — the Monday briefing](https://raw.githubusercontent.com/CJud25/GovConRadar/main/docs/screenshots/home_demo.png?v=2026-07-26)](https://govconradar.streamlit.app)

## The through-line: what each one won't do

The interesting decisions in this stack were all subtractions.

- **I built a pursuit score — feasibility × confidence × urgency — and then deleted it.** The inputs were
  screened candidates, not confirmed facts, and a score laundered a guess into something that looked
  retrieved. I also rejected the compromise of merely hiding it, because the values would still have
  flowed through hover text and prefill payloads.
- **I never published a recall figure for the link engine.** Only about **4%** of candidates match a live
  solicitation, so the set I miss is structurally unobservable and any recall number would be fiction.
  When a recency filter cut established links from **4,163 to 1,311**, I shipped the smaller number.
- **The price calculator refuses to price.** If the indirect rates were never entered, there's no headline,
  no metric, no export. An unset rate and a deliberate zero are different things — treating a blank field
  as 0% understated a real buildup by millions, so now blank means *stop*, not *zero*.
- **The compliance tool can't claim to confer status.** A machine-enforced language contract in CI blocks
  the vocabulary. Its sample org scores **89 and is still not conditionally ready**, because four open
  requirements can't be deferred to a POA&M — 88 is necessary, not sufficient.

[![CMMC Vault — sample org at 89, "Not conditionally ready"](https://raw.githubusercontent.com/CJud25/CMMCVault/main/docs/img/live-demo-sample-89.png)](https://cmmcvault-demo.streamlit.app/)

**[Start at the front door →](https://github.com/CJud25/TENS-HQ)**

---

## 🐾 Rescue Ops Workbook
*The one other people actually use.*

Everything above is evidence machinery I designed for whoever evaluates it. This one runs for whoever has
to open it on a Tuesday: a five-module Google Apps Script package handling intake and volunteer
coordination for a small dog-rescue nonprofit, installed on their live workbook and used by their
coordinators. The Contact Log doubles as new-applicant intake, so the record and the follow-up stay in one
place instead of two.

Two bugs surfaced only once real people used it — a timezone mismatch on the sheet and a phantom-row
append — and both were found *after* install. No fixture would have caught either. That's the honest gap
between building something defensible and building something used, and it's the most useful thing in my
portfolio to think about.

*Not public — it runs on a real organization's data.*

---

Also public: **[OpsPilot Command Center](https://github.com/CJud25/OpsCommandCenter)** — one framework
that ranks what to automate, proven across two unrelated operations on a single 0–100 scale.

---

*On authorship: I specify, decompose and verify; a model writes most of the line-level code. What's mine is
the specification, the slice boundaries, the decision to run an adversarial review pass at all, and the
calls about what to refuse to compute or delete. Each repo carries a `## How this was built` section that
credits those review passes with the finds rather than me.*
