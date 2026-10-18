# The Verification Gap — Data, Design & the Full Screen Set

*🔬 Ongoing research · part 3 of 3 · started 16 Aug 2026*

> Exported from the portfolio page on 2026-10-19. The live page is the canonical version: https://bhawnamanglapm.github.io/travel-tech-more.html#case-verification-gap-product-pass

- Closed the confidentiality gap first — Patronus Lynx and Vectara both confirmed self-hostable, so a draft report never has to leave the firm's network
- A full plain-language data map: what's uploaded, what stays in-house, what actually calls out
- Built in the right order: wireframe → static design → interactive prototype → landing page
- A completeness pass across every screen — navigation, buttons, sections, and the gaps still open

**Status:** where the architecture and wireframes from Part 2 got the two things they didn't have yet — a real answer to "what happens to the data," and screens built past gray boxes. Picks up at Q50.

### Q50 — "No data-handling story. This tool would ingest confidential draft reports and call out to third-party APIs (Patronus, Vectara) — a real firm will ask about that before anything else, and there's no answer yet"

A real, self-flagged gap, not a prompted one — every screen up to this point assumed data access without ever saying where the data goes. Checked whether the two AI specialists the architecture already leans on can actually run privately: **Patronus Lynx is fully open-source** (weights on HuggingFace, runnable via vLLM or Ollama inside a firm's own infrastructure), and **Vectara offers on-prem/VPC/air-gapped private deployment**. Both confirmed by search, not assumed. That single fact is what unlocks a real answer: the specialists that need to *read* the confidential draft text can be run inside the firm's own network instead of a public multi-tenant API.
   Show more: Q51–Q56 (the full data-flow map and 3rd-party touchpoints, the MVP path — design, prototype, landing page — and the full screen-by-screen completeness audit)

### Q51 — "i want to know in detail about data... where we need to input, where we will get output, from where we will fetch, where third party api involved, where api to be created etc as a layman person" / "where do we need 3rd party apis"

Walked the whole pipeline stage by stage, in plain language, and landed on **only four points where anything ever needs to leave the firm's own systems** — everything else (upload, extraction, the citation graph, the scorecard, the export) stays entirely in-house:

| Touchpoint | What goes out | Why it has to |
|---|---|---|
| Existence check | Only the citation's public URL/metadata | Has to ask the open web whether that source actually resolves — nothing confidential in the request |
| Content-match & Framing-fidelity | The draft's own sentence, to be compared against the source's sentence | The one place actual draft text leaves the parsing layer — routed to a **self-hosted** Patronus Lynx or Vectara instance, never a public shared endpoint |
| Author-verification | Only the quoted name, date, and venue | Cross-checked against a public speech/quote or news record — not the surrounding confidential paragraph |
| Legal-citation | Only the law/regulation citation string | A completely separate registry (Shepard's-style) — a different specialty API from the other three |

The layman version of the answer: everything about the report you're auditing stays on your own servers by default. The only time anything goes outside is to ask a public question ("does this URL exist," "did this person really say this," "is this citation format real") — and the one touchpoint that does need to see your actual sentences runs on a copy of the model you control, not someone else's server.

### Q52 — "what should i do to make mvp design prototype using the wireframe" / "make complete prompt from wireframe in detail" / "make prototype" → corrected: "first make design using wireframe than prototypr"

Answered the roadmap question the same way this whole thread had already earned the right to answer it — from the earlier wireframe pass, not from scratch: Wireframe (gray, structural — already done) → **Design** (static, real visual identity) → **Prototype** (interactive) → ship. Wrote a full build prompt translating the wireframes' 8 screens, their layout decisions, and the real Deloitte numbers into a build spec — then jumped straight to building the interactive prototype, skipping the middle stage. Caught directly: *"first make design using wireframe than prototypr"* — a fair, plain correction. Went back and built the missing Design stage before continuing, in the right order this time.

### Q53 — the Design stage: static, full color, five screens

Built on the wireframes' exact structure, but with a real visual identity for the first time — a deep-teal accent (`#146370`), true green/rust status colors instead of gray labels, and every number still pulled from the real audit. Five screens: Upload, Processing, Scorecard, Citation Detail — Verified, and Citation Detail — Fabricated (illustrative only, since the real audit found zero fabrications — labeled as such on the screen itself, the same discipline kept since the wireframes).

[image: High-fidelity design of the Scorecard screen in full color: a browser-style window shows the audited report's title, page and citation counts, and a Needs Review badge, above three stat tiles reading 49 Verified, 1 Fabricated, and 51 Unverifiable, a green-to-rust proportional bar, and a two-row citation table with status pills.]

The Scorecard in real color for the first time. The "1 Fabricated" tile is the illustrative example — the real audit's actual count is 0.

### Q54 — the Prototype: the same four core screens, actually clickable

Same visual system as the Design stage, this time wired up with real state — `Start audit` on Upload triggers a live Processing animation that steps through the specialists actually running, which lands on the Scorecard, which links into Citation Detail's `Confirm fabricated` / `Overturn — mark verified` / `Add note` buttons. A visible trace of the earlier data-handling answer made it into the build itself: the Upload screen carries a real **"Data sensitivity"** field alongside report type, not just a file picker — a direct, checkable link between Q50's finding and what actually got built.

### Q55 — "Create homepage style or first sign up page"

A screen that hadn't existed anywhere before this — every earlier build started at Upload, with nothing in front of it. Built as a genuine front door: a hero making the actual finding the whole pitch ("100 citations. We could only check 49."), a footnoted stat citing the audit itself, three proof-point numbers (4 of 4 Big Four firms with a fabricated-citation incident since 2024, 0 existing tools that audit a firm's own published reports end-to-end, 2 failure modes that look identical to a reader but need different fixes), a "how it works" walkthrough, and a working client-side sign-up form — work email, firm name, and report type, gated behind the same "Data sensitivity" thinking from Q50.

[image: Landing page for the Verification Gap Engine: a hero reading '100 citations. We could only check 49.' with Request early access and See how the audit worked buttons, a scorecard preview beneath it, three proof-point stats (4 of 4, 0, 2), and a How It Works section with four steps — Upload, Check, Score, Review.]

The front door the product never had until this pass — every number on it traces back to the real audit, not placeholder copy.

### Q56 — the completeness pass: "what need to be on the first screen" / "how many screens" / "what each page should have like navigation bar" / "buttons" / "sections on each page" / "add up gap pages also when if something goes wrong"

A rapid, screen-by-screen audit across everything built so far, checked against the actual files rather than answered from memory:

| Question | What the audit found |
|---|---|
| Screen count | Landing (new) + the 4-screen MVP slice (Upload, Processing, Scorecard, Citation Detail) built to design/prototype fidelity — of the 7 screens Q42 originally planned, Review Queue, Governance, Export, and Cross-report trend are still wireframe-only, not yet designed or prototyped |
| Navigation bar | A real gap, not a style choice — neither the Design stage nor the Prototype has a persistent sidebar or top nav; each screen exists as a standalone view. Flagged as unbuilt product chrome, not a deliberate minimalist decision |
| Buttons per page | Upload: `Start audit`. Citation Detail: `Confirm fabricated`, `Overturn — mark verified`, `Add note`. Landing: `Request early access` (hero + form) and `See how the audit worked` — every button traced to an actual element in the built files, not a hypothetical list |
| Sections per page | Landing breaks into 4 real sections: hero, proof-points, "how it works," and the sign-up form — each with its own job, none of them decorative |
| Gap/error states | Identified, not yet built: what a screen looks like when a document fails to parse, when zero citations are found, when every specialist times out, and when a sign-up submits with no available seats. None of these exist as screens yet — a named, open gap rather than a silent one |

### Where this goes next

Open threads, updated as they resolve:

- Answer the data-handling question a real firm asks first — done (Q50–Q51): a 4-touchpoint map, with the only content-reading specialist confirmed to be self-hostable.
- Build the Design and Prototype stages, in the right order — done (Q52–Q54): 5 static screens, then the same 4 wired up interactively, corrected mid-build to insert the design stage that was skipped the first time.
- Build the front door — a landing/sign-up page — done (Q55): a real hero, proof points, and a working sign-up form, all numbers traced to the real audit.
- Build the 3 still-wireframe-only screens (Review Queue, Governance, Export, Cross-report trend) to the same design/prototype fidelity as the MVP slice.
- Build the missing gap/error states named in Q56 — none of the four identified failure screens exist yet.
- Track C's scanner and the second-report MVP test (still open from Part 2) remain blocked on this environment's network access to a source document.

### Quick recall

| Section | Summary |
|---|---|
| **Problem** | Part 2's architecture and wireframes still had two unanswered questions a real firm asks first: what happens to the confidential draft data, and does anything exist past gray-box wireframes. |
| **Research steps** | Checked whether the two AI specialists the architecture already needed could run privately — confirmed Patronus Lynx is open-source and Vectara offers on-prem/VPC deployment (Q50) → walked the entire pipeline stage by stage and found only 4 points where anything ever needs to leave the firm's network (Q51) → built Design (5 static, full-color screens) after self-correcting a skipped step (Q52–Q53) → built an interactive Prototype wired with real state (Q54) → built a landing/sign-up page that hadn't existed before (Q55) → ran a completeness audit against the architecture and named every gap found (Q56). |
| **Solution** | A 4-touchpoint data-handling map (everything else stays in-house), 5 static design screens, a clickable prototype of the 4-screen MVP slice, and a real landing page with a working sign-up form — every number on it traced to the actual Deloitte audit, not placeholder copy. |
| **Conclusion** | The confidentiality question — the one most likely to kill the pitch on contact — now has a real, checked answer. But the self-audit (Q56) is just as important as the build: 3 of 7 planned screens are still wireframe-only, there's no persistent navigation, and 4 named failure/error states don't exist yet — named directly rather than smoothed over. |

Audited report[Deloitte Reg. Outlook 2024 →](https://nor.deloitte.com/rs/712-CNF-326/images/Regulatory-Outlook-Financial-Markets-2024.pdf) Patronus AI[Lynx model →](https://www.patronus.ai/) Vectara[HHEM & private deployment →](https://www.vectara.com/)
