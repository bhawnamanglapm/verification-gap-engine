# The Verification Gap — Research in Progress

*🔬 Ongoing research · started 14 Aug 2026, updated 18 Sep 2026*

> Exported from the portfolio page on 2026-10-19. The live page is the canonical version: https://bhawnamanglapm.github.io/travel-tech-more.html#case-ai-verification-research

- 24 problem statements mapped and sorted by who actually owns each one
- 12+ organizations traced worldwide, across 6 sectors
- India-specific: Supreme Court zero-tolerance ruling, July 2026
- Primary sources only — no blog paraphrase without a receipt
- Ran the check myself: a real, unflagged Deloitte report — 100 citations, 49 sourced, 51 not
- 16-step verification framework → a 12-stage, 3-track platform architecture

**Status:** this is a live research trail, not a finished case study — it's the groundwork behind a future build (see OpsPilot's confidence-gate pattern, applied one level up — to the deliverable itself, not just a case queue). I'm adding to it as the research goes deeper, so treat the dated entries below as a running log, not a finished table of contents.

### Why This Exists

This started as market research for a Deloitte-facing project — "what problem is a company like this actually working on, that a PM could credibly help with?" It turned into something more useful than a single pitch: a documented pattern, verified across dozens of primary sources, about what actually breaks when companies plug generative AI into real client-facing work — and, just as importantly, what *doesn't* fix it. I'm keeping this section live and adding to it as the research goes deeper, rather than freezing it as a one-time writeup.

### Current thesis (updated as this develops)

**A vendor's AI platform is built to solve a broad problem well, for millions of possible customers. It was never built to know whether it got a specific client's specific facts right in a specific deliverable.** That depth is structurally the buyer's job, not the vendor's — no procurement checklist, certification, or contract clause changes that. The gap isn't a bad vendor choice; it's a missing internal layer that has to exist regardless of which vendor a company picks.

### Full log — every question asked, every answer given

Kept verbatim, unedited, for authenticity — this is the actual research conversation, not a cleaned-up summary of it. Sources are the same links cited live during the research; a few of the longer tables below are reformatted from chat markdown into this site's table style, but the words and numbers are unchanged.
   Show more: Q1–Q26 (the original Deloitte site scan, the PM/data-management filtering, the build decision, the plain-language explainer, then the full source-hunting, global-pattern, India, platforms, regulation, and procurement thread, plus a completeness re-check and the Canada watchdog's non-investigation)

### Q1 — "i want to make fresh project for deloitte company- analyze the whole company website and various other live websites and let me know on which problem statements they are working on?"

*(`deloitte.com` and `deloittedigital.com` turned out to be blocked for direct fetching in my research environment, so this was built from indexed content, press coverage, and third-party analysis — not a raw site crawl.)*

- **Scaling agentic AI — and the governance gap behind it.** Deloitte launched Zora AI (with Nvidia) — deployable agents for finance, HR, supply chain, procurement, customer service — already running internally on expense management (claimed 25% cost cut, 40% productivity gain). Their own Tech Trends 2026 report admits only 1 in 5 companies have a mature governance model for autonomous AI agents.
- **AI output verification — and it's not theoretical for them.** In 2025, Deloitte Australia delivered a 237-page government report with fabricated citations, a made-up court quote, and nonexistent academic references — and refunded ~$290,000 USD to the Australian government.
- **Service orchestration at scale.** TrueServe (Deloitte Digital) — an agentic service-acceleration platform already running 100+ projects across 60+ clients.
- **Financial services clients** are telling Deloitte their top pressures are regulatory/compliance complexity, AI adoption vs. stablecoin/digital-asset disruption, and workforce resistance to new tools.
- **India-specific:** Project Bharat (expansion into tier-2/3 cities), Union Budget policy advisory, and real open Product Manager roles in Bengaluru/Hyderabad/Pune.

Sources: [Zora AI launch](https://www.cio.com/article/3848252/deloitte-unveils-agentic-ai-platform.html) · [Tech Trends 2026](https://www.deloitte.com/us/en/about/press-room/deloitte-tech-trends-2026.html) · [OECD.AI incident record](https://oecd.ai/en/incidents/2025-10-05-be45) · [Computerworld](https://www.computerworld.com/article/4069521/deloittes-ai-governance-failure-exposes-critical-gap-in-enterprise-quality-controls.html) · [Fortune](https://fortune.com/2025/10/07/deloitte-ai-australia-government-report-hallucinations-technology-290000-refund) · [Deloitte Digital / TrueServe](https://www.deloittedigital.com/us/en/what-we-do/digital-product.html) · [Financial services predictions](https://www.deloitte.com/us/en/insights/industry/financial-services/financial-services-industry-predictions.html) · [Deloitte India press room](https://www.deloitte.com/in/en/about/press-room/deloitte-india-establishes-presence-in-indore.html)

### Q2 — "product managers are working on which projects out of these"

Filtered the list down to what an actual Product Manager — not a strategy consultant, compliance advisor, or HR/infra team — would own:

- **Clearly PM-owned:** AI output verification/hallucination risk in client deliverables; governance maturity gap for autonomous AI agents; scaling agentic AI from pilot to production (Zora AI); AI-first process redesign vs. automating human-shaped workflows; tooling broken/suboptimized processes instead of redesigning them; service orchestration/personalization at scale (TrueServe); content supply chain fragmentation (Content Intelligence Hub); safely deploying GenAI in regulated industries (Agentforce accelerators).
- **Borderline:** translating AI ROI into enterprise financial impact (analytics/strategy usually owns the answer); AI ambition vs. stablecoin disruption in banking (becomes PM work only once it's a specific product).
- **Not PM work** (excluded): infra/security engineering, HR/L&D, org design, macro policy, compliance advisory.

Of the 8 clearly-PM ones, #1 (AI output verification) is the strongest fit — it's the one with a real, sourced, named incident behind it rather than a generic trend.

### Q3 — "data management team might work on which project out of these"

Filtered for what a Data Management team (governance, quality, pipelines/ETL, master data, privacy/access) would own — not the PM layer on top:

- **Primary fits:** content supply chain fragmentation (Content Intelligence Hub — a named content pipeline built with Adobe/AWS); service orchestration/personalization (TrueServe's underlying "customer data platforms"); data-privacy regulation compliance; safe GenAI deployment in regulated industries (data classification/access governance before an agent can act); AI output verification (the Deloitte incident was fabricated *citations* — at root, a data provenance/lineage failure); scaling Zora AI (agents are only as good as the data feeds wired into them).
- **Borderline:** translating AI ROI (data management owns the reporting pipeline feeding it, not the answer itself); re-architecting tech orgs (data architecture is one input among several).

Interesting pattern: #21, #20, #17, #24, #1, and #3 all share the same underlying skill — building and governing the data layer under an AI/personalization product.

### Q4 — "what project i should work on"

**Build #1: AI Output Verification & Provenance — a guardrail product for the exact failure Deloitte already had.** Reasoning given: it's not speculative (a named report, fabricated court quotes, a real refund, not a guessed trend); it bridges both the PM lens and the data-management lens at once; it extends an existing case study instead of starting from zero; and it's honest to build without pretending to have worked with Deloitte data.

### Q5 — "consider me a layman person and in human centric language without considering what project i have already done- focus on deloitte and make me understand the requirement, problem statement."

Explained as a story: Deloitte Australia was hired to review a welfare compliance system; AI was used to help draft the report; nobody properly checked the AI's work before it shipped; the AI invented a quote and attributed it to a real judge in a real court case, and cited academic papers that don't exist. An outside researcher found it. Deloitte had to admit it, rewrite the report, and refund the government close to $290,000.

The real reason: not that the AI is "bad" — AI tools are known to occasionally invent plausible-sounding facts. The failure was a human process failure — whoever was supposed to verify every fact and quote either didn't do it carefully, or there was no system forcing that check to happen before the document went out. Like a newsroom publishing a fabricated quote because the editor didn't fact-check it.

What's actually needed, in plain terms: a reliable checkpoint that (1) flags anything AI-generated that hasn't been independently confirmed, (2) makes it easy to trace every fact/quote/citation back to something real, (3) refuses to let a document ship until that check has happened, and (4) keeps a record of what was checked and by whom.

### Q6 — "where can i research about these things- share me links"

Grouped into: (1) the Deloitte incident itself — AI Incident Database entry, CFO Dive's two articles, Horses for Sources' industry take, with an explicit flag that outlets disagree on the refund amount ($63K–$439K depending on what's being described); (2) the general hallucination problem — Infomineo, Hatchworks, Digital Divide Data; (3) how people design the actual fix — Indium and Knostic on human-in-the-loop review, with the caveat that reviewers often approve AI output without truly verifying it when volume is high; (4) the official rulebooks — NIST AI RMF and the EU AI Act's official text, framed as "cite these, don't just cite blogs."

Sources: [AI Incident Database #1193](https://incidentdatabase.ai/cite/1193/) · [CFO Dive](https://www.cfodive.com/news/deloitte-ai-debacle-seen-wake-up-call-corporate-finance/802674/) · [CFO Dive (refund)](https://www.cfodive.com/news/deloitte-refunds-60k-report-ai-errors-australian-government-accounting/803321/) · [Horses for Sources](https://www.horsesforsources.com/deloitte-dolittle_100725/) · [Infomineo](https://infomineo.com/artificial-intelligence/stop-ai-hallucinations-detection-prevention-verification-guide-2025/) · [Hatchworks](https://hatchworks.com/blog/gen-ai/ai-hallucination-risk-assessment/) · [Digital Divide Data](https://www.digitaldividedata.com/blog/detecting-preventing-ai-hallucinations) · [Indium](https://www.indium.tech/blog/ai-hallucinations/) · [Knostic](https://www.knostic.ai/blog/ai-hallucinations) · [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework) · [EU AI Act](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng)

### Q7 — "so the incident occured in 2024, deloitte admitted in 2025, what measure steps currently deloitte is taking"

Corrected timeline: DEWR commissioned Deloitte Dec 2024; report delivered Jul 2025; a University of Sydney researcher spotted fabrications Sep 2025; Deloitte admitted, corrected, and partially refunded Oct 2025; a **second, separate incident surfaced in Canada in Nov 2025** — Newfoundland & Labrador paid ~$1.6M CAD for a 526-page healthcare-staffing report also containing fabricated citations and real researchers credited with papers they never wrote.

**What Deloitte actually did:** in Australia — corrected the report, added a disclosure statement, partial refund. In Canada — called the fake citations "incorrect," stood behind the report's recommendations anyway, promised a citation review; no refund confirmed; a provincial accounting watchdog opened its own investigation.

**The part that matters most:** no public evidence of a real fix between incident one and incident two — Canada was delivered and flagged only weeks after Australia went public. Deloitte also already sells a product for exactly this problem — "aiStudio: Large Language Model Controls," including a literal "Citation Retriever" and "RAG Evaluation" control, part of "Deloitte Trustworthy AI™" — with nothing in public reporting suggesting it was used on their own report-writing.

Sources: [CBC News](https://www.cbc.ca/news/canada/newfoundland-labrador/nl-deloitte-citations-9.6990216) · [Fortune (Canada report)](https://fortune.com/2025/11/25/deloitte-caught-fabricated-ai-generated-research-million-dollar-report-canada-government/) · [FINRA 2026 coverage](https://www.wealthmanagement.com/regulation-compliance/finra-cautions-broker-dealers-to-catch-hallucinations-when-using-gen-ai) · [The Independent (watchdog)](https://theindependent.ca/news/lji/accounting-watchdog-to-investigate-deloitte-over-fake-citations-in-1-6-million-healthcare-report/) · [aiStudio LLM Controls fact sheet](https://www.deloitte.com/content/dam/assets-zone2/de/de/docs/products/2024/aiStudio-Large-Language-Model-Controls-Fact-Sheet.pdf)

### Q8 — "which companies faced similar situations all over world- give me list"

| Sector | Entity | What happened |
|---|---|---|
| Consulting | Deloitte (Australia) | Fabricated citations, invented court quote — partial refund |
| Consulting | Deloitte (Canada) | Fake academic citations in a $1.6M healthcare report — watchdog investigating |
| Consulting | EY (Canada) | 16 of 27 sources fabricated/broken — report pulled |
| Consulting | KPMG | 40 of 45 citations fabricated or wrong in a flagship AI report |
| Law | Sullivan & Cromwell | ~28 erroneous citations in a bankruptcy motion — public apology to the Chief Judge |
| Law | Ellis George LLP & K&L Gates LLP | 9 of 27 citations fake — jointly fined ~$31,000 |
| Aviation | Air Canada | Chatbot invented a bereavement-fare policy — held legally liable |
| Government | NYC "MyCity" chatbot | Feeds business owners fabricated legal information — still live |
| Media | Chicago Sun-Times | 10 of 15 books in a "Summer Reading List" were fabricated |

Scale: as of April 2026, **1,313 documented court cases worldwide** involve AI-fabricated content, 496 involving licensed attorneys; sanctions up ~11× in 18 months. Caveat given at the time: almost everything well-documented here comes out of the US, Canada, and Australia — most likely a visibility bias (public court records, active press), not proof the problem is smaller elsewhere.

Sources: [Medium (KPMG)](https://medium.com/@creed_1732/40-fake-citations-why-kpmg-ai-report-hallucinations-should-terrify-every-enterprise-buyer-ddc1b6858e83) · [LawSites](https://www.lawnext.com/2025/05/ai-hallucinations-strike-again-two-more-cases-where-lawyers-face-judicial-wrath-for-fake-citations.html) · [Forbes (Air Canada)](https://www.forbes.com/sites/marisagarcia/2024/02/19/what-air-canada-lost-in-remarkable-lying-ai-chatbot-case/) · [Open.cx](https://www.open.cx/blog/ai-hallucination-examples) · [HAQQ](https://haqq.ai/blog/when-ai-lies-to-the-court)

### Q9 — "in india?"

| Where | What happened | Outcome |
|---|---|---|
| Supreme Court (Essel Infraprojects/NCLT) | 3 of 6 judgments relied on didn't exist; 3 real ones had invented paragraphs/wrong titles | Order quashed; zero-tolerance ruling, 2 Jul 2026 |
| Bombay High Court (KMG Wires) | Tax officer cited 3 non-existent decisions | ₹27.91 crore tax order quashed |
| Bengaluru tax tribunal | 4 non-existent case citations in an order | ~₹669 crore order recalled |
| Delhi High Court | Plea drafted via ChatGPT, fake quotes/cases | Dismissed; lawyer pulled up |
| Manipur High Court (2024) | Government pleader used ChatGPT for research | Reliability concern recorded |

The distinctive thing about India's version: the cases cluster in courts and government tax administration — not, so far, a named Indian consulting firm the way Deloitte/EY/KPMG got caught globally. Either they haven't been caught yet, or India's exposure is currently concentrated wherever the paper trail is public.

Sources: [Medianama](https://www.medianama.com/2026/07/223-10-cases-ai-hallucination-cases-in-indian-courts/) · [The Wire](https://m.thewire.in/article/law/fake-ai-cases-entered-an-nclt-insolvency-order-the-supreme-court-quashed-it-but-who-is-accountable) · [iPleaders](https://blog.ipleaders.in/ai-hallucinated-case-law-fake-citations-india/) · [ThePrint (Delhi HC)](https://theprint.in/judiciary/delhi-hc-junks-plea-crafted-by-chatgpt-with-fake-quotes-cases-what-it-said-pulling-up-erring-lawyer/2751518/)

### Q10 — "other than consulting firms which sectors and which companies made these mistakes all over world"

Tech: Google Bard's factual error in its public launch demo wiped ~$100B off Alphabet's market cap in a day; Microsoft Bing Chat gave wrong Gap/Lululemon financial figures live in its own launch demo. Media: CNET paused AI-written finance articles after errors; Gannett paused AI sports recaps after public mockery; Sports Illustrated's CEO was fired after AI-generated fake bylines. Retail/automotive: a Chevrolet dealership chatbot was manipulated into "agreeing" to sell a $76,000 Tahoe for $1. Logistics: DPD's chatbot was coaxed into swearing at a customer and calling DPD "the worst delivery firm in the world." Aviation: Air Canada held legally liable for its chatbot's invented refund policy. Government: NYC's "MyCity" chatbot still gives business owners fabricated legal information. Healthcare: a lawsuit alleges ChatGPT offered reassurance instead of urging emergency care during a serious health event. Banking: no named scandal yet, but analysts explicitly call it "not if, but when."

Pattern noted: two different failure modes — "fabrication" (Deloitte, EY, KPMG, Sports Illustrated, CNET: AI invents authoritative-looking content nobody checked) versus "loss of control" (Air Canada, DPD, Chevrolet: AI was manipulated or ungoverned in a live conversation the company had already called binding). Both point at the same missing checkpoint between "the AI said it" and "we stand behind it."

Sources: [Slashdot (Google Bard)](https://tech.slashdot.org/story/23/02/11/0632229/after-googles-ai-chatbot-made-a-mistake-its-shares-dropped-over-100-billion) · [NPR (Sports Illustrated)](https://www.npr.org/2023/11/28/1215693615/sports-illustrated-is-accused-of-posting-articles-by-writers-created-by-ai) · [AI Incident DB (Chevy Tahoe)](https://incidentdatabase.ai/cite/622/) · [TechInformed (DPD)](https://techinformed.com/dpd-disables-sweary-ai-chatbot/) · [Forbes (ChatGPT health lawsuit)](https://www.forbes.com/sites/jessepines/2026/07/26/a-lawsuit-says-chatgpt-nearly-someone-heres-the-data-on-ai-diagnosis/) · [BizTech (banking risk)](https://biztechmagazine.com/article/2025/08/llm-hallucinations-what-are-implications-financial-institutions)

### Q11 — "we have noticed gemini not giving correct output or other platforms....currently which platforms are actually responsible for all these issues that happened in deloitte and other companies"

| Incident | Platform | Confirmed? |
|---|---|---|
| Deloitte (Australia) | Microsoft Azure OpenAI — GPT-4o | Yes, disclosed in the reissued report |
| NYC "MyCity" chatbot | Microsoft Azure + OpenAI | Yes |
| Microsoft Bing Chat | OpenAI GPT-4 | Yes |
| Google Bard | Google's own Bard (Gemini's predecessor) | Yes — different, older product |
| Chevrolet dealership chatbot | "ChatGPT-powered" per reporting | Reasonably |
| Deloitte Canada, EY, KPMG | Not disclosed | No |

**Direct answer on Gemini:** Gemini is not behind any of the major professional-services scandals. Every disclosed one points to the same platform — OpenAI's GPT family via Microsoft Azure OpenAI — most likely because Azure OpenAI had the largest enterprise footprint during 2023–2025, a deployment-volume story, not necessarily a worse-model story. Pointed to the Vectara HHEM leaderboard as the real apples-to-apples comparison rather than incident anecdotes, and noted every current model still hallucinates on open-ended factual questions, Gemini included — but the paper trail on scandals specifically points at GPT-4/GPT-4o via Azure, not Google.

### Q12 — "how many such ai platforms are launched till date and their names."

No official registry exists, so no exact count — but listed the ~19 organizations the industry treats as genuinely distinct foundation-model makers: OpenAI (GPT/ChatGPT), Google DeepMind (Gemini), Anthropic (Claude), Microsoft (Copilot, built on OpenAI), Meta (Llama), xAI (Grok), Amazon (Titan/Nova), Mistral AI, Cohere (Command), Perplexity, DeepSeek, Alibaba (Qwen), Baidu (Ernie), Tencent (Hunyuan), 01.AI (Yi), Zhipu AI (GLM), Stability AI, AI21 Labs (Jamba), Databricks (DBRX), IBM (Granite) — with hundreds of significant variants below that, and thousands of consumer products built on top of this handful, not separate platforms in the same sense.

### Q13 — "what is india doing"

**Regulation:** India's Feb 2026 "AI Governance Guidelines" ("seven sutras") — an AI Governance Group, a Technology & Policy Expert Committee, an AI Safety Institute — explicitly principle-based and largely voluntary; real legal teeth currently come from the existing DPDP Act and IT Rules, not a purpose-built AI law. The guidelines themselves call for further review on generative-AI liability and accountability. Plus the judicial side already covered — the Supreme Court's July 2026 zero-tolerance ruling is doing more real enforcement than the voluntary guidelines.

**Building platforms:** under the ₹10,000 crore IndiaAI Mission, three sovereign AI models were unveiled at the Delhi AI Impact Summit — Sarvam AI's Vikram (30B) and a 105B reasoning model, Gnani.ai, and BharatGen. Plus Krutrim (Ola's AI arm, India's first AI unicorn, 22 languages), BharatGPT (already deployed at scale on IRCTC), and Bhashini (government language infrastructure).

Flagged as the sharpest angle: India is racing to build sovereign AI at government scale at the exact moment its own Supreme Court is ruling zero-tolerance on the failure mode those platforms haven't solved either — none of the three sovereign models have a publicly disclosed verification layer of their own.

Sources: [Tribune (AI Impact Summit)](https://www.tribuneindia.com/news/world/ai-impact-summit-2026-indias-ai-governance-guidelines-anchored-by-seven-sutras-to-drive-safe-trusted-innovation/) · [Official PIB guidelines PDF](https://static.pib.gov.in/WriteReadData/specificdocs/documents/2026/feb/doc2026215790801.pdf) · [explainx.ai](https://explainx.ai/blog/india-sovereign-ai-status-indiaai-mission-2026) · [Business Standard](https://www.business-standard.com/technology/tech-news/india-ai-impact-summit-2026-sovereign-models-sarvam-bharatgen-gnani-126021900417_1.html) · [Rest of World](https://restofworld.org/2026/india-frugal-ai-sarvam-krutrim-sovereign/)

### Q14 — "names of platforms other than those 19"

Added, with sourcing: Nvidia (Nemotron, and the "Nemotron Coalition" open-model alliance whose founding members include India's own Sarvam AI); TII/Falcon (UAE); Moonshot AI (Kimi, China); MiniMax (China); Huawei (Pangu — the only Chinese firm with both a frontier model and its own AI chips); Naver (HyperCLOVA X, Korea); LG AI Research (EXAONE/K-EXAONE, a government-backed Korean sovereign-model project); Samsung (health-specific foundation models). Plus a lighter-confidence list flagged as "not re-verified this session": Inflection AI (Pi), Character.AI, Snowflake (Arctic), Salesforce (xGen/Agentforce), Aleph Alpha, Sakana AI, Preferred Networks (PLaMo), Baichuan, StepFun, SenseTime, iFlytek.

### Q15 — "and if any company launch their own ai platform - what measures are taken that it can be used."

**Legally required, by region:** EU — mandatory pre-market conformity assessment for high-risk systems (real law, real penalties). China — mandatory CAC security assessment + algorithm filing before public reach. US and India — no binding pre-launch requirement; NIST's AI RMF and India's guidelines are both explicitly voluntary. Outside the EU and China, a company can currently launch to the public with no prior approval from anyone.

**What companies do on their own regardless of law:** red-teaming (adversarial testing, documented with exact prompts and severity); model cards / system cards (published limitations and evaluation results); company-specific frameworks (Anthropic's Responsible Scaling Policy, Google DeepMind's Frontier Safety Framework, OpenAI's Preparedness Framework); staged rollout. Explicitly quoted the researchers' own caveat: "red-teaming practices vary widely, and there are few established standards or best practices" — closer to an honor system than an inspection.

Tied back to Deloitte directly: there was no CAC-style filing or EU-style conformity assessment standing between Deloitte and using AI in that report — the only thing that could have caught it was Deloitte's own internal review, which is exactly the layer that failed.

Sources: [VDE (EU AI Act conformity assessment)](https://www.vde.com/topics-en/artificial-intelligence/blog/conformity-assessment-high-risk-ai) · [FPF (China's Generative AI Measures)](https://fpf.org/blog/chinas-interim-measures-for-the-management-of-generative-ai-services-a-comparison-between-the-final-and-draft-versions-of-the-text/) · [Innodata (AI red teaming)](https://innodata.com/generative-ai/model-safety-evaluation-and-red-teaming/) · [Towards AI (model/system cards)](https://pub.towardsai.net/ai-safety-in-practice-red-teaming-evaluation-and-guardrails-for-enterprise-genai-deployments-c38f2463506e)

### Q16 — "what all are actual legal documents - share me links"

Split into binding law (EU AI Act official text on EUR-Lex; China's Interim Measures for Generative AI Services, via China Law Translate and the CAC original; India's DPDP Act, 2023, via the official Gazette and India Code) versus guidance/frameworks that aren't codified statute (NIST AI RMF; India's AI Governance Guidelines PDF via PIB; FINRA's 2026 Annual Regulatory Oversight Report). Flagged explicitly: only the first group is actually law with penalties attached — the second is guidance, and conflating the two is exactly the kind of precision gap that got Deloitte in trouble.

Sources: [EU AI Act (EUR-Lex)](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng) · [China's Generative AI Measures (translation)](https://www.chinalawtranslate.com/en/generative-ai-interim/) · [CAC original (Chinese)](http://www.cac.gov.cn/2023-07/13/c_1690898327029107.htm) · [DPDP Act (Official Gazette)](https://egazette.gov.in/WriteReadData/2023/248045.pdf) · [DPDP Act (India Code)](https://www.indiacode.nic.in/bitstream/123456789/22037/1/a2023-22.pdf) · [NIST AI RMF](https://www.nist.gov/itl/ai-risk-management-framework) · [India AI Governance Guidelines](https://static.pib.gov.in/WriteReadData/specificdocs/documents/2026/feb/doc2026215790801.pdf) · [FINRA 2026 Report (PDF)](https://www.finra.org/sites/default/files/2025-12/2026-annual-regulatory-oversight-report.pdf) · [FINRA guidance page](https://www.finra.org/rules-guidance/guidance/reports/2026-finra-annual-regulatory-oversight-report)

### Q17 — "is there any other document that is left"

Added three more, since "legal document" specifically was asked: India's IT Rules, 2021 (Intermediary Guidelines and Digital Media Ethics Code), official MeitY-hosted PDF; *Mata v. Avianca, Inc.* (S.D.N.Y. 2023) — the original, most-cited AI-hallucination sanctions ruling, via CourtListener; *Moffatt v. Air Canada*, 2024 BCCRT 149 — the actual tribunal decision, via CanLII. Noted honestly that I could not find direct links to the Indian court orders discussed earlier (Supreme Court, Bombay HC, Bengaluru tribunal, Delhi HC, Manipur HC) since Indian judgments aren't reliably indexed by general web search — pointed to the Supreme Court's own judgment portal and Indian Kanoon as the right places to search directly instead of taking an unverified link on faith.

Sources: [IT Rules, 2021 (MeitY PDF)](https://www.meity.gov.in/static/uploads/2024/02/Information-Technology-Intermediary-Guidelines-and-Digital-Media-Ethics-Code-Rules-2021-updated-06.04.2023-.pdf) · [Mata v. Avianca (CourtListener)](https://www.courtlistener.com/docket/63107798/mata-v-avianca-inc/) · [Mata v. Avianca (full opinion PDF)](https://www.law.berkeley.edu/wp-content/uploads/archive/2025/12/Mata-v-Avianca-Inc.pdf) · [Moffatt v. Air Canada (CanLII)](https://www.canlii.org/en/bc/bccrt/doc/2024/2024bccrt149/2024bccrt149.html)

### Q18 — "what all details a company needs to submit to govt to ensure their AI models /platforms are working correctly"

**EU AI Act Annex IV — the 9-section technical file** (binding 2 Aug 2026, high-risk systems only): general description; design & development details including training/validation/testing data governance; monitoring, functioning & control; performance metrics (accuracy, robustness, cybersecurity); risk management; a lifecycle-changes log; applied standards; a signed EU Declaration of Conformity; a post-market monitoring plan.

**China's CAC algorithm filing** (within 10 working days of launch): algorithm name, type, intended purpose, technical mechanism, plus a security self-assessment report on a CAC template; only a limited public summary is disclosed (category, entity name, product, purpose, Beian filing number). 988 services filed, 598 app-level registrations completed as of mid-2026.

**Everywhere else:** nothing required. And the sharper point: neither real regime explicitly requires "prove every citation/fact in AI-generated output is real" — the EU governs the system in aggregate, China's filing is about the algorithm being registered, not auditing every document produced with it. Even where governments do require submissions, none of them ask the one question that would have caught Deloitte's actual failure.

Sources: [EU AI Act — Annex IV (official text)](https://artificialintelligenceact.eu/annex/4/) · [AppInChina (China's AIGC filing, plain-language)](https://appinchina.co/blog/what-is-chinas-aigc-filing/)

### Q19 — "before purchasing any AI tool what all things do companies verify"

Model quality (accuracy for the specific use case, disclosed hallucination rates, offline evaluation support, version-comparison); data handling (what happens to data sent to the tool, whether it trains the vendor's model, access controls, data residency); certifications (SOC 2 as baseline, ISO/IEC 42001 for AI management systems specifically, ISO 27001); contract clauses (ban on training on your data without consent, audit rights, 24–72h incident-notification SLA, no silent model swaps, clear liability/indemnification, a real exit/data-deletion plan); and ongoing monitoring — re-reviewing vendor certifications every 2–3 years or after any serious incident, not just once at signing.

Closed with the gap this doesn't cover: none of this verifies whether any specific document a team produces using the tool is actually true — vendor due diligence and output verification are two separate control layers, and most companies only build the first.

Sources: [ACC (Procuring AI)](https://www.acc.com/procuring-ai-key-considerations-and-strategies) · [InfosecTrain (ISO 42001)](https://www.infosectrain.com/blog/how-iso-42001-helps-in-ai-procurement-vendor-risk) · [Internet Lawyer (10 clauses)](https://www.internetlawyer-blog.com/drafting-ai-vendor-contracts-the-10-clauses-that-protect-your-business/)

### Q20 — "So deloitte purchased this right? Deloitte (Australia, welfare report) Microsoft Azure OpenAI — GPT-4o"

Confirmed: yes, almost certainly through an existing enterprise Microsoft relationship. Ran that against the Q19 checklist directly — SOC 2 ✅, ISO 27001 ✅, data residency controls ✅, no-training-on-data terms ✅ standard, established auditable vendor with SLAs ✅. **Deloitte would have passed nearly every item.** The vendor was not the problem — Microsoft/Azure OpenAI is one of the most heavily audited, certified platforms in existence. What Deloitte didn't have, and no vendor contract can supply, is a process step internal to Deloitte checking whether the specific citations in that specific report were real before it reached the client. Framed as the project's core insight: "Deloitte didn't fail at picking a trustworthy AI vendor. They failed at the one check no vendor relationship can ever cover: verifying their own output before a client saw it."

### Q21 — "so it means deloitte or any company can buy any tool- but they shld also have internal tool that verifies if that tool is giving right output as per their clients bcs vendor might have large problem statement solved but we need to go in depth"

Confirmed and sharpened into one line: **a vendor's AI tool is built to solve a broad problem, well, for millions of possible customers. It was never built to know whether it got a specific client's specific context, or a specific deliverable, right. That depth is always the buyer's job, never the vendor's.** Explained why structurally: the vendor doesn't know the company's client, industry-specific facts, or what "correct" means in that specific deliverable — only the company itself has that context. So every company using AI needs a second, internal layer between "the AI produced this" and "we're sending this to a client" — one that can't be bought off the shelf, because buying it would just recreate the same problem one level up.

### Q22 — "give me answer to all these questions and then i will decide on what i need to go in detail" (India-specific consulting firms, a real hallucination-rate comparison, and what Deloitte has actually changed internally)

**1) Any Indian consulting firm caught yet?** Not found — but the global pattern got bigger while looking. It's now **all four of the Big Four**, not three: KPMG's withdrawn Oct 2025 report fabricated specific claims about real, named clients (UBS, NHS Greater Manchester, Swiss Federal Railways, and a false claim that Emirates launched a chatbot called "Sara"); EY pulled a May 2026 loyalty-fraud report citing a McKinsey report that doesn't exist; and **PwC** was confirmed too — four separate PwC Middle East "thought leadership" reports (2024–2026) with fabricated citations, one assessed as 100% AI-generated once references are excluded, including an entirely invented governance framework called "Citizen Pulse." On India specifically: nothing found linking an Indian firm or engagement — only a mildly ironic Deloitte India press release on the same timeline titled "Indian enterprises lead global peers in at-scale AI adoption."

**2) Real hallucination-rate comparison (Vectara HHEM leaderboard):** two pictures exist. On the older, easier benchmark, Gemini models lead (Gemini-2.0-Flash at 0.7%). On the harder, Feb 2026 dataset (32K-token documents across legal/medical/financial domains), rankings shuffle and everything gets worse — GPT-5.4-nano 3.1%, Gemini 2.5 Flash-Lite 3.3%, Grok 3 5.8%, Claude Haiku 4.5 9.8%, Claude Opus 4.6 12.2%, Gemini 3 Pro 13.6%. The finding that matters: on the harder test, every current state-of-the-art reasoning model exceeds 10% hallucination regardless of vendor — Vectara's own hypothesis is that reasoning models' extra "thinking" steps introduce drift from the source, so more capable models get *worse*, not better, on this specific failure mode.

**3) What Deloitte's actually changed internally:** Deloitte's own position hasn't moved — still "stands by the recommendations" on Canada, still frames it as a citation-verification lapse. The real change came from the *client*, not Deloitte: Newfoundland & Labrador rewrote its own procurement process within days — mandatory human verification, audit rights over vendor AI use. That's a client protecting itself from Deloitte, not Deloitte fixing itself.

Sources: [ThePrint (all four Big Four)](https://theprint.in/feature/pwc-big-four-ai-hallucination-kpmg-ey-deloitte/3002405/) · [OECD.AI (KPMG)](https://oecd.ai/en/incidents/2026-06-12-b883) · [GPTZero (PwC investigation)](https://gptzero.me/news/investigations-pwc/) · [Vectara (leaderboard)](https://www.vectara.com/blog/introducing-the-next-generation-of-vectaras-hallucination-leaderboard) · [Canadian Accountant (NL procurement update)](https://www.canadian-accountant.com/content/profession/cpanl-deloitte-ai-scandal)

### Q23 — "Lets get on 3rd problem" (deeper dive on Deloitte's internal response)

Found a brand-new, dated announcement — **ControlCatalyst.AI**, launched 12 Aug 2026 (days before this conversation), a suite for internal audit/SOX/risk-controls work, built on the same "Deloitte Trustworthy AI™" branding as the pre-Australia "aiStudio" product. Chased down what it actually does: automates control testing and evidence documentation for *client* engagements — the same pattern as aiStudio, a product sold to clients, not a fix aimed at Deloitte's own report-writing process. **Verdict:** this is the third AI-governance product shipped since Australia, and the third one aimed at what Deloitte sells rather than the specific internal failure that happened twice. The launch timing — 3 months after Canada, weeks after PwC's scandal broke — reads more like catching up on positioning industry-wide than a purpose-built response to this exact failure.

Sources: [Deloitte press release](https://www.deloitte.com/us/en/about/press-room/deloitte-announces-launch-of-controlcatalyst-ai.html) · [CPA Practice Advisor](https://www.cpapracticeadvisor.com/2026/08/05/deloitte-introduces-controlcatalyst-ai/188027/) · [TechEdgeAI](https://techedgeai.com/deloitte-launches-controlcatalyst-ai-to-bring-agentic-ai-to-enterprise-risk-and-compliance/)

### Q24 — "what all tools/websites/apps like ControlCatalyst.AI are present in market"

Three distinct market layers, not one:

**Layer A — direct SOX/GRC competitors:**

| Tool | What it is |
|---|---|
| Optro (formerly AuditBoard) | Category leader — SOXHUB heritage, 1,585+ G2 reviews at 4.6/5, Fortune 500 + Big Four advisory partnerships |
| Workiva | 4,000+ customers, 75% of Fortune 500 — links SOX controls evidence directly to source financial data and SEC filings |
| Diligent One Platform | Audit management + continuous monitoring, AI analyzing 100% of transactional data, not sampling |
| KPMG's own "TACO" framework | An agentic-AI governance framework reusing SOX's ICFR structure — notable since KPMG is also the firm that got caught fabricating an agentic-AI report |

**Layer B — the tools that actually caught the Big Four:**

| Tool | What it is |
|---|---|
| GPTZero | The tool literally used in the KPMG, EY, and PwC investigations. Originally an academic-integrity plagiarism detector, now doing citation-fabrication forensics on Big Four reports. Acquired by Superhuman (Grammarly), June 2026 — $88M valuation, 19M+ users, $30M ARR |
| Originality.AI | Competing AI-content detector; its integrated fact-checker flags fabricated statistics, wrong dates, and unverified attributions. Enterprise API available ($136–179/mo) |

**Layer C — enterprise LLM output-verification infrastructure** (the category closest to a real project):

| Tool | Positioning |
|---|---|
| Patronus AI | Open-source "Lynx" hallucination detector, plus domain-specific evaluators (finance, legal, healthcare, copyright) |
| Galileo | Real-time runtime guardrails — sub-200ms inline blocking of unsafe/hallucinated responses before they reach a user |
| Arize | LLM evaluation platform, hallucination/relevance scoring, LLM-as-judge, strong RAG support |
| Guardrails AI | Open framework (RAIL) for enforcing structure and validation rules on LLM output |

**The honest read:** Layer C is not empty — it's real, funded infrastructure. What doesn't exist anywhere publicly is the specific product decision to wire that infrastructure into one firm's actual report-delivery workflow. That's a PM gap sitting on solved technology, not a technology gap.

Sources: [RiskWatch](https://www.riskwatch.com/audit-management-software/) · [Originality.AI (GPTZero review)](https://originality.ai/blog/gptzero-ai-content-detection-review) · [Braintrust (hallucination detection tools)](https://www.braintrust.dev/articles/best-hallucination-detection-tools-2026) · [Galileo vs. Patronus](https://galileo.ai/blog/galileo-vs-patronus)

### Q25 — "what pm gap missing didnt understand, tell me in detail"

Explained with the actual proof it's real: Deloitte already owned a citation-checker (aiStudio's "Citation Retriever") before Australia, and it still shipped fabricated citations anyway. The technology wasn't the problem. The smoke-detector analogy: owning a detector doesn't stop a fire unless someone's also decided which rooms need one, who checks the battery, what happens when it beeps, and who's accountable if it was dead for months. Six concrete decisions nobody's making at Deloitte: (1) does the check run on every report or only some; (2) where in the workflow does it run; (3) what confidence score is "good enough" to ship without a human; (4) whose job is it to actually check a flagged item; (5) what happens when someone overrides it under deadline pressure; (6) who's accountable if the whole thing gets silently bypassed. None of these are technology questions — they're business-process decisions, which is the actual, portable definition of what a PM does here that a detection vendor never will.

### Q26 — "check whether our research work was complete or something left. And then check how government and deloitte are working together" (18 Sep 2026)

**Completeness check on this log:** Q1–Q25 hold up — every question has a primary source, and the "Where this goes next" list below was already fully resolved or pointing forward into Part 2/3. The real gaps are in the build, not the research: Part 2 is explicitly one audited report with Track C never run, and Part 3 has 4 of 7 planned screens still wireframe-only — both honestly labeled already, both blocked on this environment's network access to a source PDF, not on missing research.

**New finding — Canada's accountability gap just got worse, not better.** CPA NL (the professional accounting watchdog covering Newfoundland & Labrador) opened an investigation into Deloitte's fabricated citations in the $1.6M healthcare report — and in May 2026 closed it **without investigating anything**, on a legal-entity technicality: the report was delivered under a contract with "Deloitte Inc.," which isn't a CPA NL-registered firm, while "Deloitte LLP" (the firm that *is* registered) "was not a party to the contract and had no involvement in the report." Nobody has been held accountable for that report by anyone. This directly extends the project's own thesis from Q7/Q22 — not just that no internal fix is visible, but that the external oversight mechanism that might have forced one has now formally declined to look.

**A correction, not an addition — checked and ruled out.** A South Africa story surfaced in the same search results (a government AI policy pulled in April 2026 after 6 of 67 citations turned out to be fabricated) and it would have been easy to log as a fifth Big Four incident. Checked directly: it isn't one. The policy was drafted internally by South Africa's own Department of Communications and Digital Technologies under Minister Malatsi — no consulting firm named in any source as author or vendor. Noting this explicitly rather than silently skipping it, since conflating two similar-sounding stories is exactly the kind of unverified-citation error this whole research thread is about.

**No evidence found** that any government has cut ties with, blacklisted, or restricted new contracts to Deloitte specifically because of these incidents. Newfoundland & Labrador's procurement-process tightening (already logged at Q7) remains the only concrete governmental response on record — and now the one oversight body that could have added a second is off the table.

Sources: [The Independent (investigation opened)](https://theindependent.ca/news/lji/accounting-watchdog-to-investigate-deloitte-over-fake-citations-in-1-6-million-healthcare-report/) · [Ricochet Media (investigation closed)](https://ricochet.media/politics/provinces/atlantic/deloitte-used-ai-in-1-6m-government-report-but-watchdog-says-it-cant-investigate/) · [Canadian Accountant](https://canadian-accountant.com/content/profession/cpa-nl-deloitte-ai) · [ANC Parliamentary Caucus (South Africa statement)](https://ancparliament.org.za/statement-on-minister-malatsis-use-of-artificial-intelligence-in-drafting-south-africas-national-ai-policy/) · [CNBC Africa (South Africa policy pulled)](https://www.cnbcafrica.com/2026/south-africa-pulls-ai-policy-after-hallucinated-citations-expose-drafting-scandal)

### Where this goes next

Open threads, updated as they resolve:

- Find out whether any Indian consulting firm has had a Deloitte-style incident yet — checked (Q22): not found; the pattern instead expanded to all four of the Big Four globally.
- Get a real hallucination-rate comparison across GPT/Gemini/Claude — checked (Q22): Vectara HHEM leaderboard reviewed; on the harder 2026 benchmark, every current frontier model exceeds 10%, regardless of vendor.
- Track what Deloitte's actually changed internally — checked (Q23): ControlCatalyst.AI (12 Aug 2026) is a third client-facing product, not an internal-deliverable fix — still no public evidence of the specific gap being closed.
- Re-check whether any oversight body has actually held Deloitte accountable — checked (Q26): CPA NL closed its Newfoundland & Labrador investigation in May 2026 without investigating, on a legal-entity technicality. No government has restricted new contracts to Deloitte over any of this.
- Design the actual internal verification layer this points toward — see the execution-roadmap exercise, a role-play working through exactly this as a hypothetical Deloitte PM.
- The research continues directly into the actual hands-on audit and the platform it led to — see Part 2: From Audit to Prototype.

### Quick recall

| Section | Summary |
|---|---|
| **Problem** | Started as an open question — "what problem is a company like Deloitte actually working on, that a PM could credibly help with?" — and surfaced a real, documented pattern: AI platforms are built to answer broadly, not to verify a specific client's specific facts, and two AI-fabricated Deloitte reports, an EY report pulled for 16 fabricated sources, and a KPMG report with 40 of 45 citations wrong all trace back to the same missing layer. |
| **Research steps** | Mapped 24 problem statements by who actually owns each one (Q1–Q10) → traced the pattern across 12+ organizations and 6 sectors worldwide, sourced only to primary documents (Q11–Q21) → ruled out a look-alike (South Africa's policy pull — checked and correctly excluded, Q26) → diagnosed the actual gap as 6 unmade business-process decisions, not a technology gap (Q25) → re-checked accountability as late as Sep 2026 and found Canada's oversight body closed its investigation without investigating (Q26). |
| **Solution** | Not proposed yet at this stage — this part is diagnosis, not a build. The actual verification-platform architecture comes out of the hands-on audit in Part 2, and the org-adoption plan for it is the role-play execution roadmap. |
| **Conclusion** | The gap is real and sourced, not assumed — confirmed across 12+ organizations, not one incident. The honest, portable finding: owning detection technology (Deloitte already had a citation-checker before Australia) doesn't fix anything until someone makes the business-process decisions around it — which is the actual, non-technical job a PM does here. |

EU AI Act[full text →](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng) NIST AI RMF[framework →](https://www.nist.gov/itl/ai-risk-management-framework) Mata v. Avianca[court record →](https://www.courtlistener.com/docket/63107798/mata-v-avianca-inc/) PwC investigation[GPTZero →](https://gptzero.me/news/investigations-pwc/) Vectara leaderboard[next-gen benchmark →](https://www.vectara.com/blog/introducing-the-next-generation-of-vectaras-hallucination-leaderboard)
