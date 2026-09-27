# Access profile and source routing

## Institutional and subscription access

If the user profile lists institutional, library, or paid-database access (e.g. a university network with ScienceDirect, Springer, IEEE, JSTOR, a society's digital library), treat it as a *reported* capability. The institution, portal, collections, and browser authentication are not verified until observed. It is permission to use available access for requested research, not proof that every article is covered. Do not infer the user's discipline from it.

For an identified paper, try its publisher record and full text using the available institutional browser/network session. Inspect the actual result: readable HTML/PDF, abstract only, login, purchase page, or error. Do not assume a remote search backend has the same access as the user's local browser. Use observed publication links instead of guessing journal endpoints.

If sign-in is needed, let the user sign in through the service; do not request credentials in chat or extract cookies or tokens. Continue searching public sources while access is unresolved. Do not purchase articles or contact librarians/authors without authorization. A request to research does not authorize sending messages.

## Full-text discovery

When a needed paper is inaccessible, look for a matching DOI/title in the publisher's open version, an institutional repository, an author's public manuscript, or a relevant preprint repository. Verify title, authors, year, and version. A preprint or accepted manuscript can differ from the final article; label it. Use discovery services such as Unpaywall or OpenAlex if available without inventing API access.

Use only legitimate access routes: publisher open access, institutional access, repositories, author copies, and preprints. If a pivotal paper cannot be read, say so and label conclusions that rely on its abstract. Never use unavailable text to support details inferred from an abstract.

## Select source families by question

These are candidate destinations, not claims of current connectivity. Apply the mandatory Reddit/YouTube search and broad social/media coverage rules in [social-and-media.md](social-and-media.md). Check availability during the actual task.

| Need | Candidate routes | Evidence handling |
| --- | --- | --- |
| Scholarly discovery | Publisher search, Google Scholar, Semantic Scholar, OpenAlex, Crossref, field-specific indexes | Index records identify papers; inspect the paper or explicitly label abstract-only evidence. |
| Engineering and physical sciences | Publisher platforms (ScienceDirect, Springer, IEEE, society digital libraries) via any institutional access; relevant society journals; arXiv and institutional repositories | Compare experimental conditions, model assumptions, units, validation, and versions. |
| Biomedical questions | PubMed, PMC, appropriate guidelines and study registries | Distinguish study design, registration, population, outcomes, and publication status. |
| Russian-language scholarship (example of a regional family) | eLIBRARY, CyberLeninka, university repositories and dissertation catalogs | Distinguish an indexed record from available full text; verify translated terminology. |
| Datasets and code | Original data repositories, Zenodo, OSF, official code repositories | Check provenance, versions, licenses when reuse is relevant, and reproducibility limits. |
| Historical documents and missing pages | Internet Archive / archive.org, Wayback Machine, digitized library collections | Record capture date separately from publication date. A snapshot establishes historical content, not current truth. |
| Experience and emerging issues | Reddit, specialist forums, technical communities | Read context and dates; treat anecdotes as leads or reported experience. Votes are not scientific validation. Avoid broad prevalence claims from selected comments. |
| Practical projects and software | Official documentation, original specifications, issue trackers, reproducible comparisons, relevant communities | Prefer primary technical sources. Check date/version and separate vendor claims from independent evidence. |
| Region-specific questions | Local-language government, university, professional, and community sources | Search native names and scripts; do not extrapolate a local result globally. |

Search Reddit as requested even when it may yield no useful results; do not force irrelevant results into the answer. Do not exclude non-journal material when the question concerns lived experience, historical content, implementation problems, or gray literature. Include video, short-form social content, photographs, and specialist communities using [social-and-media.md](social-and-media.md).

## Optional: DuckDuckGo configuration reference

Checked September 2026: [official URL parameters](https://duckduckgo.com/duckduckgo-help-pages/settings/params) list `kl=wt-wt` for no region. Its [source explanation](https://duckduckgo.com/duckduckgo-help-pages/results/sources) says traditional links and images are largely sourced from Bing. No-region settings are not a guarantee of neutrality or worldwide coverage. Recheck if behavior or settings differ.
