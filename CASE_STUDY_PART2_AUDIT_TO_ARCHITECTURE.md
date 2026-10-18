# The Verification Gap — From Audit to Prototype

*🔬 Ongoing research · part 2 of 3 · started 15 Aug 2026*

> Exported from the portfolio page on 2026-10-19. The live page is the canonical version: https://bhawnamanglapm.github.io/travel-tech-more.html#case-verification-gap-platform

- Ran the check myself: a real, unflagged Deloitte report — 100 citations, 49 sourced, 51 not
- 16-step verification framework → a 12-stage, 3-track platform architecture
- 8 screens wireframed, designed, and built into a clickable prototype
- A real landing page, sign-up flow, and honest launch-readiness check

**Status:** where the research turned into hands-on work — the actual citation audit, the verification framework it produced, and the platform architecture, wireframes, design, and prototype built from it. Picks up exactly where Part 1 left off, at Q26.

### Q26 — "ok lets start here" (sourced a real, unflagged Deloitte report and ran the actual check)

Moved from research to hands-on audit. Sourced Deloitte's **"Regulatory Outlook for Financial Markets 2024"** — a real, public, 56-page Deloitte Centre for Regulatory Strategy report, not one of the already-flagged scandal reports. First check: a discrepancy-detection pass on structural completeness — do the in-text citation numbers and the bibliography actually match. Counted every citation marker across all 56 pages by hand and cross-validated the total by summing page-by-page (32 through page 10, +23 = 55 through page 24, +20 = 75 through page 39, +25 = 100 through page 50 — the sum lands exactly on the highest in-text number, confirming the manual count was accurate). Then opened the Endnotes section: it lists entries **1 through 49 only**. **Citations 50 through 100 — 51 of the report's 100 in-text citations, just over half — have no bibliography entry anywhere in the document.**

Audited document: [Deloitte — Financial Markets Regulatory Outlook 2024 (PDF, hosted on deloitte.com)](https://nor.deloitte.com/rs/712-CNF-326/images/Regulatory-Outlook-Financial-Markets-2024.pdf)

### Q27 — "what is citation first explain in simple terms" / "how many citations each page have"

A citation is just a receipt — a small number in the text that points to exactly where a claim came from, so a reader can go check it themselves instead of taking the author's word for it. Delivered the full per-page count across all 56 pages as the evidence base for the structural check above.
   Show more: Q28–Q49 (the verification methodology, the full 51-row unverifiable-citation map, the 16-step framework, the market scan, and the entire platform architecture, wireframes, and prototype)

### Q28 — "what all steps should i plan by which i shld verify each thing in the document"

Formalized an 8-step verification methodology, each step mapped to what would need to be built to automate it:

| # | Step | What it checks |
|---|---|---|
| 1 | Structural completeness | In-text citation count vs. bibliography entry count — cheap, automatable, and the one that caught the real finding |
| 2 | Existence check | Does each citation's URL resolve and match a real, findable source |
| 3 | Content-accuracy check | Does the source actually say the claim — the hard, AI-model-dependent step |
| 4 | Named-author verification | Cross-check quoted speakers/authors against a real publication database |
| 5 | Statistical/data-point verification | Does the quoted number match the source's number |
| 6 | Self-citation consistency | Flag when the publisher cites itself |
| 7 | Recency/currency check | Has a cited fact since gone stale or been contradicted |
| 8 | Sampling/coverage threshold | Not automatable — the PM-owned policy call on how much unverifiable content is acceptable to publish |

### Q29 — "now check each citation by going the link provided and see if statement is there"

Hit a real environment wall first: WebFetch came back `EGRESS_BLOCKED` on every domain tested — including a completely neutral sanity-check domain with zero sensitivity, confirming it wasn't a Deloitte-specific block but a full outage. Pivoted transparently to WebSearch as the verification method instead — same rigor, different tool. Result: **all 49 present endnotes independently checked out as real** — correct organization, correct date, correct author, topically accurate — across sources including DNB, IMF, World Bank, BIS, ESRB, IOSCO, BCBS, EIOPA, FSB, ECB, Bank of England, the European Commission, the Federal Reserve, UK Finance, Reuters, and Deloitte's own site. Two details worth flagging: endnotes #40 and #46 cite the identical "Future of Payments Review" report for two different points (redundant, not wrong), and #49 is a **self-citation** — Deloitte citing its own report on digital-asset regulation.

Then mapped every one of the 51 uncited citations (50–100) to its exact page and claim — the evidence that turns "roughly half is unsourced" into something concrete and checkable. The five below are the ones that matter most — specific, quotable statistics presented with the exact same confident formatting as the 49 verified ones, with no way for a reader to tell, just by looking at the page, which citations are checkable and which aren't:

| # | Pg | The specific claim it's attached to |
|---|---|---|
| 65 | 32 | **"£740 billion (around 55%) of all lending to UK businesses" comes via NBFIs** |
| 81 | 44 | **"49% of portfolio managers and 69% of stockbrokers had identified no vulnerable consumers"** |
| 96 | 49 | **Private credit grew "from less than USD 60 billion in 2002 to over USD 1.3 trillion in H1 2022"** |
| 99 | 50 | **Global private-equity dry powder hit "USD 2.69 trillion in December 2023"** |
| 100 | 50 | **Deloitte's own "ESG in Private Capital Survey 2023"** — 69 respondents, 61 firms, "91% already having ESG policies" — a second, uncredited self-citation |

   Show all 51 — every citation, every claim, not just the five above (the full page-by-page map)

| # | Pg | The specific claim it's attached to |
|---|---|---|
| 50 | 23 | Spain has postponed its MiCAR compliance deadline to December 2025 |
| 51 | 23 | Licence timings "vary between two weeks and two years across the EU27" |
| 52 | 23 | Bitcoin/Ether daily trading-volume chart (source: CoinMarketCap) |
| 53 | 23 | Firms should prepare for "heightened scrutiny" on digital-asset licensing |
| 54 | 24 | Major jurisdictions pushing ahead with their own national AI approaches |
| 55 | 24 | AI use-case chart (source: Warwick Business School) |
| 56 | 28 | ECB imposing "periodic penalty payments" on SSM banks |
| 57 | 28 | UK regulatory-fines chart (source: PRA, FCA) |
| 58 | 29 | EBA issued revised guidelines on resolvability |
| 59 | 29 | PRA will review branch-vs-subsidiary thresholds |
| 60 | 29 | Near-final EU CRD6/CRR3 text published |
| 61 | 29 | Near-final UK capital policy published |
| 62 | 29 | Large banks capitalised to absorb "a very significant credit shock" |
| 63 | 29 | "Evidence" cited from 2023 bank failures |
| 64 | 29 | Reverse stress tests (RST) recommendation |
| 65 | 32 | **"£740 billion (around 55%) of all lending to UK businesses" comes via NBFIs** |
| 66 | 32 | "Senior supervisors" question effectiveness of indirect NBFI regulation |
| 67 | 33 | ECB published Oct 2023 review of CCR governance practices |
| 68 | 33 | PRA identified CCR management shortcomings |
| 69 | 33 | FCA found poor client-relationship management |
| 70 | 35 | Reference to "SUK reforms" |
| 71 | 36 | FSCS branch liability cap of £500m |
| 72 | 37 | "New rules on MOBI" came into effect end of 2023 |
| 73 | 37 | FCA says wholesale market has "a long way to go" on inclusive culture |
| 74 | 38 | Supervisors advocate "impact underwriting" |
| 75 | 39 | Insurers must attest annually to Fundamental Spread/MA sufficiency |
| 76 | 41 | FCA plans to review the advice/guidance boundary in 2024 |
| 77 | 43 | Info-sharing needed for product governance/value assessments |
| 78 | 43 | FCA's 2024 review of Duty embeddedness |
| 79–80 | 43 | FCA highlighted firms not passing on a fair share of revenues |
| 81 | 44 | **"49% of portfolio managers and 69% of stockbrokers had identified no vulnerable consumers"** |
| 82 | 45 | "Significant shortcomings" in the FCA's fund-liquidity review |
| 83 | 45 | PRA's model risk management principles |
| 84 | 46 | IOSCO guidance on swing-pricing market-impact modelling |
| 85 | 46 | FSB recommendation against daily dealing for illiquid-asset funds |
| 86–87 | 47 | DC/DB pension investment-opportunity measures |
| 88 | 47 | The Mansion House Compact |
| 89 | 47 | The LTAF (UK) |
| 90 | 47 | ELTIF II (EU) |
| 91 | 47 | New EU loan-origination-fund regime |
| 92 | 47 | IOSCO warning on rate-driven default/valuation risk |
| 93 | 47 | Regulators calling for more private-market transparency |
| 94 | 47 | ESMA's CSA on valuation risks |
| 95 | 48 | PRA model risk management principles (repeat citation) |
| 96 | 49 | **Private credit grew "from less than USD 60 billion in 2002 to over USD 1.3 trillion in H1 2022"** |
| 97 | 49 | FCA raised concerns re: high-risk/complex investments sold to wealth clients |
| 98 | 50 | Deloitte's "own analysis" on fee-discount value |
| 99 | 50 | **Global private-equity dry powder hit "USD 2.69 trillion in December 2023"** |
| 100 | 50 | **Deloitte's own "ESG in Private Capital Survey 2023"** — 69 respondents, 61 firms, "91% already having ESG policies" — a second, uncredited self-citation |

### Q30 — "so what all checks we did and what we did miss? what shld be the roadmap"

Self-audit against the 8-step framework: fully done — structural completeness, existence checks on all 49. Partial — content-accuracy (topic-level match confirmed, not full sentence-level verification) and self-citation (2 found, not run as a systematic sweep). Not done — named-author verification beyond 2 spot checks, statistical re-verification of every number, and recency (now actually possible in hindsight, since 2024 forward-looking predictions can be checked against what really happened by 2026). Turned that gap analysis into a 7-phase build roadmap — structural scan first (cheapest, catches the most), then existence + topical match, then the hard content-accuracy layer, then statistics, author-verification, self-citation/circularity, recency monitoring, and a governance policy layer last.

### Q31 — "what else is missing in 8 step framework"

Pushed past execution gaps into methodology gaps — failure modes the 8 steps don't even have a step for. Found 7 more, restructured into 5 tiers by what kind of work each actually needs:

| Tier | Adds | Catches |
|---|---|---|
| 1 — Structural | Citation-placement accuracy | A marker attached to the wrong claim in the same paragraph — a real bug found on page 29, where a duplicated paragraph reused an old citation number |
| 2 — Semantic | Framing fidelity | A true fact used out of context — a caveat dropped when quoting a source |
| 2 — Semantic | Derived-statistic methodology | A number the report calculated itself from raw source data, not quoted verbatim — is the math shown and correct |
| 3 — Provenance | Chain-of-custody | A "source" that's just relaying someone else's number a hop removed — citation laundering |
| 4 — Temporal | Internal consistency | The report contradicting itself across pages |
| 4 — Temporal | Library-level pattern check | Whether a firm's self-citation rate, or a repeated-but-superseded claim, is trending across its whole publication history — invisible if every audit is per-document |
| 5 — Governance | Materiality/risk-weighting | Nothing on its own — it's the triage layer deciding which citations get the deepest scrutiny (headline stat vs. background aside) instead of spending a fixed budget evenly |
| 5 — Governance | Remediation workflow | What happens after something's found wrong — retraction, versioning, notifying anyone who already relied on it. Detection without this is a dead end |

### Q32 — "what all websites exist working on these frameworks"

Fresh market scan against the 5-tier structure — the finding is the shape of the gap, not any single tool:

| Layer | Players | What they actually cover |
|---|---|---|
| Structural | SwanRef, CiteCheck, RefCheck-AI | Academic-paper citations only — 150M+ papers via Crossref/Google Scholar, binary real-or-fake |
| Semantic | Patronus AI (Lynx), Galileo (Luna), Vectara (HHEM-2.3) | Live RAG-answer faithfulness, in the moment a chatbot responds — not auditing a finished, already-published PDF |
| Provenance | GPTZero, Originality.AI | Academic/AI-content plagiarism forensics — the tool literally used to catch KPMG, EY and PwC, but built for papers, not corporate reports |
| Legal-specific | Lexis+ / Protégé, NexLaw | Case-law and statute citations only |
| Governance | Workiva, Diligent, AuditBoard, Deloitte's own ControlCatalyst.AI | Internal SOX/financial controls — not the credibility of a firm's own published thought-leadership |

Every specialist tool is built for a different document type, a different moment (live generation vs. after publish), or a different purpose (internal controls vs. public credibility). Nobody stitches structural + semantic + provenance + governance together, aimed at a firm's own published research output — the whitespace this whole thread has been pointing at.

### Q33 — "explain me the gap in layman language"

Every existing tool is a specialist checkpoint doing one narrow job — a bouncer checking student IDs (SwanRef), a spell-checker built into a live chatbot (Patronus/Vectara), a plagiarism detector at a university (GPTZero), a lawyer's citation checker (Shepard's/NexLaw), or the internal-audit team checking a company's own books (Workiva/Diligent). Nobody's built the full check-up doctor — the one who takes a firm's own published report and runs it through every layer at once, and specifically tells you where the sourcing simply stops and nobody flagged it. That's exactly what the manual walkthrough of the Deloitte report proved by hand this week.

### Q34 — "what all things need to be checked in full report"

Consolidated into a 10-item, end-to-end audit checklist: (1) document-wide structural count-match, (2) per-citation existence/attribution/topic/claim/context/placement, (3) every number and statistic, (4) every chart's data source, (5) every quote and named person, (6) self-referencing, (7) internal consistency across the document, (8) currency — did a forecast actually hold up, (9) the materiality-and-coverage decision of which claims matter most, (10) what happens after something's found wrong. This list is what the platform's architecture is a direct build-spec for.

### Q35 — "does it cover — nobody has built the 'full check-up' doctor"

Mapped the 10-item checklist against the market scan, item by item, to confirm the gap is real and not just a hunch: existence/attribution (academic tools only), content-match (live-chat tools only), context/caveat-dropping (nobody, anywhere), citation-placement (nobody), derived-statistics (nobody), chart sourcing (nobody), self-citation as a standing feature (nobody), internal consistency (nobody), currency re-checking after publish (nobody), and materiality/remediation workflow (GRC tools have it, but for internal controls, not public reports). Confirmed: every specialist tool is either the wrong document type, the wrong moment in time, or the wrong purpose — the "full check-up" really doesn't exist yet.

### Q36 — "what if each speciality is built so that the system is not heavy and correct output is given"

The instinct is exactly how these systems actually get built in the industry, not a simplification — confirmed against the market research itself (Braintrust, on the current RAG-eval landscape: "there is no single tool that does everything — a production stack layers an eval framework, a faithfulness checker, an observability platform, and an inline guardrail"). Laid out the shape: a cheap parsing layer runs on 100% of citations first; a router decides which specialists a given citation actually needs (a $-figure gets the statistics specialist, a quote gets author-verification, most citations trigger 2–4 of the roster, never all of them); each specialist stays small and narrow — several can be bought/integrated (Patronus, Vectara) instead of built; a lightweight aggregator combines verdicts into one score; governance sits on top as pure rules, no model at all. The real product becomes the router and the governance layer, glued around a handful of licensed specialists plus the handful nobody else has built.

### Q37 — "what all specialisations are there"

Full roster, organized by what signal in a citation triggers each one:

| Trigger | Specialist | What it checks |
|---|---|---|
| Always runs | Existence | Does the source resolve, is it real |
| Always runs | Attribution | Right org, date, author |
| Always runs | Content-match | Does the source support this specific sentence |
| Always runs | Placement | Is the marker attached to the right claim, not an adjacent one |
| Always runs | Self-citation | Does the source domain match the publisher's own domain (near-free, pure logic) |
| $ or % figure | Statistics-match | Does the number match the source |
| Report's own calculation | Derived-calculation | Is the math shown and correct |
| Chart/graph caption | Chart-data | Does the visualized data match the source |
| Named person + quote | Author-verification | Is the quote real, right date/venue |
| Secondary/news source | Chain-of-custody | Primary source, or laundered through one |
| Law/regulation reference | Legal-citation | Different registry entirely (Shepard's-style) |
| Forecast/deadline language | Currency/recency | Has this since been superseded or contradicted by events |
| Caveat in the source | Framing-fidelity | Was the caveat dropped when the report used the fact |
| Repeated fact in-doc | Internal-consistency | Do the two instances agree |
| Matches a past report | Cross-report/library | Contradiction or repetition across the firm's own history |
| Not a checker | Materiality/risk-weighting | Decides how deep the other specialists should go, based on where the citation sits (headline vs. footnote) |

### Q38 — "what should be steps to check and conclude which route to go and which specialisation to be selected"

The router's actual decision sequence, run for every citation: (1) isolate the exact sentence and source attached to the marker; (2) the existence gate — no bibliography entry at all means stop immediately, flag unverifiable, nothing else runs (this single gate alone caught citations 50–100 in the real audit); (3) run the baseline 5 unconditionally; (4) classify the claim by scanning for $/% figures, quotes, forecast language, chart attachment, legal references, secondary sourcing, and attach only the relevant specialists; (5) score materiality separately, in parallel, deciding depth rather than which specialist runs; (6) aggregate every specialist's verdict into one tier — green/amber/red — with a full evidence record; (7) escalate anything uncertain or high-materiality to a human instead of auto-closing; (8) feed the human's decision back to sharpen future classification.

### Q39 — "create a complete architecture from document extraction to final output"

Full 12-stage pipeline, grounded in the real Deloitte audit at every stage:

| # | Stage | Does |
|---|---|---|
| 1 | Extraction | Parses text, footnote markers, chart captions, quotes, and the bibliography as separate structured fields |
| 2 | Citation Graph Builder | Links every marker to its exact claim and its bibliography entry, or null — the stage that alone surfaces the structural gap |
| 3 | Classification & Routing | Tags each citation with which specialists it actually needs |
| 4 | Specialist Verification | Runs only the triggered specialists in parallel, each a small, swappable service |
| 5 | Materiality Scoring | Scores prominence — pull-quote/headline vs. supporting detail |
| 6 | Unified Scorecard | Combines everything into one master table — never blends the buckets |
| 7 | Escalation / Review Queue | Routes anything uncertain to a human, with evidence pre-assembled |
| 8 | Governance Policy Engine | Pure rules — a firm's configured coverage threshold decides publish/hold/review |
| 9 | Output / Export | Generates the shareable audit report |
| 10 | Post-Publication Monitoring | Re-checks existence and currency on a schedule after the report ships |
| 11 | Cross-Report Library | Indexes every audited report — surfaces pattern-level trends a single document can't |
| 12 | Data stores | Five persistent stores backing the pipeline: Citation Graph DB, Source Cache, Review/Audit Log, Policy Config Store, Report History Index |

### Q40 — "remember our main target is to find AI Hallucination"

An important correction, caught before it became an overclaim: what the manual audit found on the Deloitte report is **unverifiable**, not **hallucinated** — those are different claims. Hallucinated means the AI invented something that never existed. Unverifiable means there's nothing to check against; the claim could be entirely true. Re-sorted all 16 specialists against the real target: only 5 — Existence, Content-match, Author-verification, Statistics-match, Chain-of-custody — actually prove fabrication. Everything else (structural completeness, placement, self-citation, framing-fidelity, internal-consistency, currency, materiality/governance) is real report-hygiene value, but it isn't hallucination detection, and the pitch has to stay precise about which is which.

### Q41 — "create an architecture for a platform — if required divide it into two things hallucination and unverifiable"

Split the pipeline into two tracks right after the Citation Graph stage, forking on one question — does this citation have a source at all: **Track A** (has a source) runs the 6 fabrication-proving specialists and can only output Real, Fabricated, or Suspicious. **Track B** (no source) runs a light 3-step check and can only ever output Unverifiable — it never touches the specialists that would let it claim fabrication, because there's nothing to check against. The two converge into a scorecard with 3 separate, non-blendable counts. Scored against the real report: **49 Verified · 0 Hallucinated · 51 Unverifiable** — the honest number, not the inflated "51 hallucinations" headline it would've been easy to overstate.

### Q42 — "what shld i make to have complete steps — architecture/wireframe/roadmap"

Recommended three linked deliverables: the **architecture** (the fork, the 12 stages, the specialist tiers, build-vs-buy calls); **wireframes** for the 7 screens a real user would need — upload, the scorecard dashboard, a per-citation detail view, the review queue, governance settings, the export report, and a cross-report trend view; and a **roadmap** sequencing the build so the sharpest claim ships first — Track A only (Existence, Content-match, Author-verify) as the MVP, then Track B and governance, then the remaining specialists, then monitoring, then the cross-report library.

### Q43 — "now make a user diagram for complete architecture including internal architectures" (three review-and-fix passes, run against my own critique each time)

Built the diagram, then deliberately audited it against everything discussed above rather than treating a first draft as done. Round 1 found real gaps: Self-citation was missing from the specialist grid entirely, despite being the check that caught Deloitte citing itself twice in the real audit. Framing-fidelity and Internal-consistency — the two most differentiated, least-built checks in the whole market scan — were also missing. The Verdict Resolver could output "Suspicious," but the Scorecard only had 3 buckets, so a Suspicious verdict had nowhere to go. Materiality was described in a text label but never actually drawn as a real signal reaching the router. And the 5 data stores from the written spec were invisible on the diagram entirely.

Fixed all of it in two more passes: added a 4th, dashed-border **Pending** bucket so Suspicious verdicts can't silently disappear; drew a real materiality-signal line from Stage 1 into both tracks instead of just labeling it; drew all 5 data stores as their own elements with real connectors, including the one — Source Cache — that's genuinely read twice, once at first-check and again by Monitoring, months later. Then one more correction: re-checked whether "AI hallucination" — the stated goal — actually covered fabricated numbers, fabricated authors, *and* self-made claims with no citation at all. It didn't. Everything in the pipeline was triggered by a citation marker existing in the first place — a bare, uncited assertion stated as flat fact was invisible to the whole system. Added a third track, **Track C**, branching directly off Stage 1 before the citation graph is even built, scanning all uncited text for real factual claims and labeling them a 5th bucket: **Unsupported Assertion** — deliberately never confused with Unverifiable, because "cited but the trail ran out" and "never even tried to cite anything" are different failures with different fixes.

[image: Verification Gap Engine architecture diagram: a document flows through extraction and citation-graph building, then forks into three tracks. Track B (amber, no source) runs a 3-step check ending in Unverifiable. Track A (rust, has a source) runs a materiality-aware classifier dispatching 12 parallel specialists into a verdict resolver producing Real, Fabricated, or Suspicious. Track C (violet, branching off extraction directly) scans uncited body text for unsupported factual claims. All three converge into a 5-bucket scorecard — Verified, Hallucinated, Unverifiable, Pending, Unsupported — feeding materiality scoring, a dashed-border human-run escalation stage, governance policy, and output, before splitting into monitoring and a cross-report library, with five labeled data stores and a trend-data feedback loop back to the top.]

The current architecture: three tracks (Hallucination-checked / Unverifiable / Never-cited), 12 pipeline stages, 12 specialists, and all 5 data stores — nothing left as a label-only fix. [Download the full diagram as a PDF →](https://bhawnamanglapm.github.io/projects/verification-gap-engine/Verification-Gap-Engine-Architecture.pdf)

### Q44 — "at what step ai hallucination is checked" / "are fabrication of numbers, authors, and self-made claims all covered"

Precise answer, not a hand-wave: eligibility is decided at the fork (only Track A citations can ever be tested for fabrication); the actual checking happens across the 12-specialist grid; but the verdict itself — the single point allowed to output "Fabricated" — is the Verdict Resolver, one step after the grid. Nowhere else in the pipeline may produce that label. On coverage: fabricated numbers (Statistics-match, Derived-calc), fabricated authors/quotes (Author-verify), and fabricated sources (Existence) were all genuinely covered — but self-made claims with no citation at all were not, until Track C closed that specific hole.

### Q45 — "create wireframe for each screen"

Built deliberately low-fidelity — gray boxes, one shared sidebar shell so all screens read as one product, and every label pulled from the real Deloitte audit rather than lorem ipsum: **49 Verified · 0 Hallucinated · 51 Unverifiable · 0 Pending · — Unsupported** throughout.

[image: Wireframe of the Scorecard screen: five stat tiles for Verified, Hallucinated, Unverifiable, Pending, and Unsupported, a proportional stacked bar showing 49% verified and 51% unverifiable, a gate-status badge reading Needs Review, and a citation table with status chips and materiality ratings.]

The Scorecard — the headline view, gate status and the 51% gap visible before reading a single row.

### Q46 — "now check wireframe and compare with User diagram — does it cover everything?"

Ran a real gap review, not a self-congratulation pass. Found: 8 of 12 pipeline stages had screen coverage, but Stages 1–3 (Extraction, Citation Graph, the Fork itself) had no visible processing state at all. Bigger problem — because the real audit came back with 0 Hallucinated and 0 Pending, **every wireframe example only ever demonstrated the boring outcomes.** No screen showed what it actually looks like when the system catches a fabrication, what a human sees mid-review with confirm/override buttons, or what Track C's detail view even looks like (it needs a genuinely different layout — no source panel makes sense when nothing was ever cited). Also flagged: only 5 of 12 specialists were ever shown running in any one example, and the Review Queue had no record of past reviewer decisions, only Governance's separate policy log.

### Q47 — "add all missing details"

Closed every gap from the review: added a new **Processing** screen showing Stages 1–4 actually running as a live checklist. Expanded Citation Detail from one example to **four full verdict states** — Verified (real), Fabricated (illustrative, since the real audit found none, marked clearly as such), Pending under review (with the Confirm Verified / Confirm Fabricated / Request more evidence buttons that were missing entirely), and Unsupported — Track C's own layout, with no source panel and a different, 2-item specialist set. Gave Review Queue its own decision log, separate from Governance's. Added a cache timestamp to citation examples, giving the Source Cache store — invisible until now — an actual UI presence.

### Q48 — "add on all specialists in form of drop down or something in roster"

Rather than force all 12 specialists into every example (unrealistic — a typical citation only triggers 2–5), added one real, working reference: a native `<details>` dropdown listing the complete 12-specialist roster with what triggers each one and what it checks, linked directly from every Track A example ("5 of 12 shown — view full roster →"). It's a genuinely functional disclosure, not a static image pretending to be one — the artifact is live HTML, so it actually expands and collapses.

[image: Wireframe of the Citation Detail screen showing all four verdict states stacked: Verified (Klaas Knot speech, matched source), Fabricated (a fake Cambridge Centre for Financial Ethics survey, with specialists failing existence and attribution checks, and confirm/overturn buttons), Pending under review (a partial-match claim with reviewer decision buttons), and Unsupported Assertion under Track C (no source panel, just a claim with no citation ever attached). Below all four, an expanded dropdown lists the full 12-specialist roster with trigger conditions and what each checks.]

Citation Detail's four verdict states, plus the full 12-specialist roster reference below them. [Download all 8 screens as a PDF →](https://bhawnamanglapm.github.io/projects/verification-gap-engine/Verification-Gap-Wireframes.pdf)

### Q49 — "now compare this wireframe with actual tools present in world currently" / "so our is good to be launched in marketing through Deloitte"

Benchmarked each screen against real products instead of reasoning from memory. **Citation Detail's split-panel layout is close to Turnitin's Similarity Report** (matched-text-left, source-right, click to filter) — a mature UX pattern borrowed from plagiarism detection, not invented. **Review Queue matches Optro's** (formerly AuditBoard) own description of its dashboards: "purpose-built... automatically updated in real-time... quickly see what is in their queue." **Governance's threshold-alerting concept is confirmed by Workiva's** GRC platform. But the Scorecard's 5-way bucket split has no real precedent — GPTZero, SwanRef, and Vectara's leaderboard all collapse to one score or rate, never distinguishing "checked and fine" from "never checked." And Monitoring's per-firm trend concept has no precedent either — Vectara's leaderboard trends rates across different *models*, not one publisher's own report history. The finding: this product stitches together two tool categories that have never been combined — citation-checkers' simple in/out interaction, and GRC platforms' workflow/governance machinery.

On whether it's launch-ready: no, and worth being precise about why. What's real — the problem (found by hand, on an actual report), the market gap (confirmed against real tools, not assumed), and a complete, internally consistent architecture. What's missing before an actual pitch — zero working product code, a sample size of one audited report, Track C never actually run, no cost or data-handling story, and no adoption path inside a real firm. There's a real difference between this being the strongest answer in an interview room and this being ready to send to Deloitte's leadership — right now it's clearly the former, not yet the latter.

### Where this goes next

Open threads, updated as they resolve:

- Run a real citation-fabrication check on an actual public Deloitte report myself, using the same method that caught KPMG/EY/PwC — done (Q26–Q29): 100 in-text citations, 49 bibliography entries, all 49 confirmed real, 51 unverifiable — with the exact claim behind every one of the 51 mapped out.
- Turn the 8-step framework and the checklist into an actual product architecture — done (Q36–Q43): a 12-stage, 3-track platform architecture (Hallucination-checked / Unverifiable / Never-cited), full specialist roster, and a complete system diagram.
- Wireframe the screens this architecture implies — done (Q45–Q48): 8 screens, all four verdict states, the full 12-specialist roster, benchmarked against real tools (Q49) — a sample size of one report and zero working code, so not launch-ready, and said so plainly.
- Build Track C's actual scanner and run it against the same Deloitte report — the one bucket on the scorecard that's still a "—", not a number.
- Prototype the MVP slice (Existence + Content-match + Author-verify only) against a second, different unchecked report — still on a sample size of one until that happens.
- Both of the above are still open — this environment's network access to the source PDF is currently blocked, so neither could be run for real yet. Meanwhile the build side kept moving — the data-handling question, the actual design and prototype, a landing page, and a full screen-by-screen completeness pass: see Part 3: Data, Design & the Full Screen Set.

### Quick recall

| Section | Summary |
|---|---|
| **Problem** | Part 1 diagnosed the gap; this part asks whether it's really there — sourced a real, unflagged, public Deloitte report and ran the citation check by hand instead of trusting the pattern found in others' incidents. |
| **Research steps** | Audited the report structurally — 100 in-text citations vs. 49 bibliography entries (Q26) → built an 8-step verification method, then expanded it to 16 failure modes across 5 tiers (Q28, Q31) → scanned the market and found no tool stitches structural+semantic+provenance+governance together (Q32–Q35) → corrected scope from "hallucination" to a precise 3-way split after catching the risk of overclaiming (Q40–Q41) → designed and audited a 12-stage, 3-track architecture through 3 self-review passes (Q39, Q43) → wireframed 8 screens and benchmarked them against real products (Q45–Q49). |
| **Solution** | The Verification Gap Engine's 12-stage, 3-track pipeline (Hallucination-checked / Unverifiable / Never-cited), a 12-specialist roster triggered selectively per citation, and 8 wireframed screens — all grounded in the real audit's actual numbers, not placeholder data. |
| **Conclusion** | 49 Verified · 0 Hallucinated · 51 Unverifiable — the honest result, not the inflated "51 hallucinations" headline it would've been easy to claim. The architecture is real and benchmarked against actual competing tools, but it's a sample size of one report with zero working code — the strongest answer in an interview room, not yet something to pitch to a real client. |

### Which feature is used at which step

| Feature | Used at |
|---|---|
| **Citation Graph Builder** (Stage 2) | Right after extraction — links every marker to its claim and bibliography entry, or null; the single stage that alone surfaced the real 49/51 split |
| **Track A / B fork** | Right after the citation graph — separates "has a source, testable for fabrication" from "no source, stays Unverifiable," so the system can never overclaim hallucination where the honest label is unverifiable |
| **12-specialist roster + router** | Classification & Routing (Stage 3) through Specialist Verification (Stage 4) — only the specialists a given citation type actually needs ever fire |
| **Materiality scoring** | Stage 5 — decides how deep the specialists go (headline stat vs. background aside), not which ones run |
| **Escalation / Review Queue** | Stage 7 — routes anything uncertain to a human, with evidence pre-assembled, instead of auto-closing it |
| **Governance Policy Engine** | Stage 8, before Output — pure rules deciding publish/hold/review against a firm's configured coverage threshold |
| **Post-Publication Monitoring + Cross-Report Library** | Stages 10–11 — re-checks currency/existence on a schedule after a report ships, and surfaces patterns across a firm's whole publication history |

Audited report[Deloitte Reg. Outlook 2024 →](https://nor.deloitte.com/rs/712-CNF-326/images/Regulatory-Outlook-Financial-Markets-2024.pdf) SwanRef[citation checker →](https://www.swanref.org/) GPTZero[ICLR 2026 findings →](https://gptzero.me/news/iclr-2026/)
