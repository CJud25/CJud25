## Hi there 👋

**I build operational decision systems that turn messy queues and compliance constraints into ranked action.**

Operations Analyst / BI + Automation. I work the whole path — public data → validated model → a screen a
decision-maker can act on — and I label what's a fact, what's an estimate, and what the tool refuses to guess.
Every project below ships its tests, a CI workflow, and an honest facts-vs-estimates boundary.

---

## 🛰️ GovCon Recompete Radar
*Which expiring DoD cyber/IT contracts are worth pursuing — and which numbers you can defend.*

An ETL + BI pipeline over public **USAspending.gov / SAM.gov** data that finds expiring DoD cyber/IT contracts,
scores each for pursuit fit, and **quarantines the records it can't stand behind** instead of dressing them up as
leads. Ships a DuckDB SQL pack, a Power BI star schema, and a Streamlit app.

> **Outcome:** 324 tests, a data-contract validator (scorer parity to 0.0), a six-query DuckDB pack, and a
> "Competitive Price Range" that refuses to estimate below a comparables floor. Fixing an expired-record scoring
> bug moved the Tier-1 count from an inflated 118 to an honest **25**.

[![GovCon Recompete Radar — the Monday briefing](https://raw.githubusercontent.com/CJud25/GovConRadar/main/docs/screenshots/home_demo.png)](https://cjudk25.streamlit.app)

**[Live demo](https://cjudk25.streamlit.app)** · **[Repo](https://github.com/CJud25/GovConRadar)** · **[Case study](https://github.com/CJud25/GovConRadar/blob/main/docs/case-study.md)**

---

## 🧭 OpsPilot Command Center
*One framework that ranks what to automate, across very different operations.*

Find the bottleneck → price the fix → rank the work → generate the leadership brief → run a safe micro-automation.
Proven on **two domains at once** — a business service desk and a nonprofit dog rescue — on a single 0–100 scale.

> **Outcome:** 20 tests (up from a suite `pytest` couldn't even collect), 75% coverage, CI on Python 3.12/3.13.
> ROI is conservative labor-savings **net of build + maintenance cost**; every figure is labeled illustrative, and
> two fabricated ROI metrics were removed with a test that keeps them gone.

[![OpsPilot Command Center — executive overview](https://raw.githubusercontent.com/CJud25/OpsCommandCenter/main/docs/img/command-center.png)](https://opscommandcenter.streamlit.app/)

**[Live demo](https://opscommandcenter.streamlit.app/)** · **[Repo](https://github.com/CJud25/OpsCommandCenter)** · **[Case study](https://github.com/CJud25/OpsCommandCenter/blob/main/docs/case-study.md)**

---

## 🛡️ CMMC Vault
*The compliance number that looks like a finish line but isn't.*

A session-only tool that scores a **NIST SP 800-171 / CMMC Level 2** self-assessment the way the DoD does — and
makes one missed truth impossible to ignore: a score of **88 is necessary but not sufficient**. The sample org
scores **89 yet is not conditionally ready**, and the tool turns that gap into an ordered remediation plan.

> **Outcome:** 63 tests, **98% coverage** of the core logic, a CI-gated catalog-integrity check, and a
> machine-enforced language contract so the tool can never claim to confer CMMC status. It's a readiness
> self-estimate — never a certification.

[![CMMC Vault — sample org at 89, "Not conditionally ready"](https://raw.githubusercontent.com/CJud25/CMMCVault/main/docs/img/hero-dashboard.png)](https://cmmcvault-demo.streamlit.app/)

**[Live demo](https://cmmcvault-demo.streamlit.app/)** · **[Repo](https://github.com/CJud25/CMMCVault)** · **[Case study](https://github.com/CJud25/CMMCVault/blob/main/docs/case-study.md)**

---

*The numbers above are produced by commands in each repo, not asserted — clone one and run the three-command quickstart.*
