# Source quality, evidence registry, critique, and final verification

Adapted from: the SIFT / lateral-reading method used by university libraries; daymade/claude-code-skills deep-research (source-type labels, concentration limits, freshness flags, citation registry as gatekeeper, counter-claim sentences, per-section confidence, "information black box"); 199-biotechnologies/claude-deep-research-skill (red-team personas, critique loop-back with delta queries, citation validation); Imbad0202/academic-research-skills (claim-faithfulness audit, concession threshold against sycophancy).

## 1. Evaluate unfamiliar sources with SIFT (lateral reading)

For any source that will carry a consequential claim and whose reliability is not already obvious:

- **Stop** — notice when a source is unfamiliar, emotionally charged, too good to be true, or selling something.
- **Investigate the source** — read *about* the site/author/channel elsewhere (who runs it, expertise, funding, track record), rather than judging from its own "About" page or design.
- **Find better coverage** — look for the same claim in stronger or independent sources; often faster than deep-reading a weak one.
- **Trace to the original** — follow quotes, statistics, images, and "studies show" back to the primary document, study, dataset, or original creator, and check the context was preserved.

Keep this quick for low-stakes everyday tasks; do it carefully for health, money, safety, legal, and contested claims.

## 2. Label every useful source

In the registry, give each source:

- **Type**: `official` (maker, standard, regulator, docs) · `academic` (peer-reviewed, preprint — say which) · `expert-practitioner` (demonstrated hands-on expertise) · `journalism` · `industry/vendor` · `community` (Reddit, forums, comments) · `social-video` (YouTube, TikTok, Instagram, Facebook) · `archive` · `other`.
- **Access level**: full text read · partial · abstract only · metadata/snippet only · video watched/transcript only · via NotebookLM (cited passage checked / answer only — see notebooklm.md) · archived copy.
- **Date** (publication and, for time-sensitive claims, the "as of" date of the fact).
- **Evidence family**: which other sources it depends on (same study, same press release, reposted clip).
- **Interest**: sells the product, funded by party X, affiliate links, none known.

## 3. The evidence registry is the gatekeeper

- Build the registry while searching. Before writing, make an **evidence-mapped outline**: each planned section lists its key claims and the registry entries supporting them. Gaps become delta queries, not prose.
- The final text may cite only sources in the registry. URLs come only from pages actually retrieved; never construct a URL, DOI, page number, timestamp, or author from memory.
- **Concentration check**: if one source (or one evidence family) carries more than about a third of the load-bearing claims, look for independent support or say explicitly that the conclusion rests mainly on it.
- **Freshness**: for fast-moving facts (prices, versions, availability, regulations, software behavior, "best current" anything), prefer sources from the last 6–12 months and state the as-of date; older sources get a note. Foundational science, history, and physical technique do not expire this way.
- **Information black box**: when searches find nothing on a subquestion, record what was searched (channels, languages, queries) and say so. Do not fill the hole with plausible reasoning presented as findings.

## 4. Confidence, disagreement, and inference

- Mark confidence per major claim or section, not one score for the whole report: **high / medium / low** (in the output language), each with a short reason (e.g. "two independent primary sources", "only Reddit reports", "single study, n=12").
- In any section where credible sources disagree, include at least one sentence stating the strongest counter-claim and why you weigh it as you do.
- Separate three layers in wording: what sources report · what authors interpret · what you infer or propose. Label your adaptations ("my suggestion, not a tested recipe").

## 5. Critique loop (Standard: light; Deep/Exhaustive: required)

After the first full draft (or evidence-mapped outline for long reports), review it through distinct lenses. Pick those that fit the task:

- **Skeptic** — Which claims are weakly supported, single-sourced, outdated, or from interested parties? What would make the recommendation wrong?
- **Practitioner / beginner doing it tomorrow** — Could someone actually follow this? Which step, quantity, tool, or condition is missing or vague? What will they get stuck on?
- **Domain expert** — What would an expert notice is wrong, outdated, or oversimplified? What standard source is conspicuously absent?
- **Other-language / other-region reader** — Is anything country-specific (availability, law, units, brand names) presented as universal?

Turn each critical issue into a **delta query** and go back to search (max 2–3 loops). Minor issues are fixed in text. Stop when no critical issue remains or budget ends; list anything unresolved.

## 6. When the user pushes back

Treat the user's objection as a new claim to check, not an instruction to agree. Re-examine the evidence; change the answer when the objection brings new facts, a better source, or exposes an actual error — and say what changed. If the evidence still supports the original answer, keep it politely and show why. Never flip merely to please.

## 7. Final verification pass (always)

Before delivering:

1. For each load-bearing citation, re-open or re-read the supporting passage and confirm it says what the text claims (numbers, units, conditions, population, date, version). Downgrade or remove claims that fail.
2. Check that no URL, DOI, timestamp, quote, or count was invented or carried over from memory.
3. Check quotes are short and rare; everything else in your own words.
4. Check the brief answers the actual question asked and that the coverage note is honest (what was searched, what was blocked, what was not tried).
5. For code, calculations, or numbers you derived: run them if a runtime is available; otherwise say they are untested.

For high-stakes Deep reports, when a subagent tool is available and permitted, have a fresh agent that did not write the report perform steps 1–2 on the finished text.
