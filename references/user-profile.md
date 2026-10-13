# User profile (optional — fill in to personalize)

Use this file as a generic template. Keep personal preferences in a private local copy or in an explicitly configured external settings file; do not commit them to the distributed package. If no settings are configured, use the defaults in the right column. Keep secrets out of profiles: never put passwords, API keys, cookies, or tokens here.

| Setting | Your value | Default if empty |
| --- | --- | --- |
| External settings location | | None; use this template's defaults |
| Output language | | Language of the user's request |
| Extra search languages (always try) | | Chosen per topic (English + the user's language + topic-relevant ones) |
| Default depth tier | | Standard |
| Mandatory channels (always attempt) | | Reddit, YouTube |
| Extra channels for broad research | | TikTok, Instagram, Facebook, X/Twitter, Threads, forums, image search, Telegram (when topic fits) |
| Excluded sources | | None |
| Preferred general search engine | | Whatever search tool is available; optionally DuckDuckGo `kl=wt-wt` via browser |
| Signed-in services the agent may read with (browser) | | None assumed; discover at run time |
| NotebookLM (plan; may create notebooks and add sources) | | Not used |
| Institutional / library access | | None assumed |
| Where to save long reports | | Chat reply for short answers; a Markdown file or the host's document format for long ones |
| Anything else (tone, units, country for prices/availability) | | Infer from conversation |

## Example (delete or replace)

```
Output language: Russian
Extra search languages: Russian, English
Default depth tier: Standard
Mandatory channels: Reddit, YouTube, Telegram
Signed-in services: Telegram Web and YouTube in the agent's browser (read-only use)
NotebookLM: Pro plan — may create research notebooks and add sources
Institutional access: university network — ScienceDirect, Springer (via browser session)
Country for prices/availability: Germany
```

## Rules for using this profile

- Preferences here are defaults; the current request always wins.
- If the user or host explicitly configures external settings, read the current files and use their confirmed preferences. In personal-assistant this means its core rules and the configured vault's `Агенты/Настройки.md` and `Агенты/Память.md`; other hosts may use different paths. Do not assume those files or the plugin exist, search unrelated vaults, or create a guessed profile when they are missing. Report material access gaps and continue with generic defaults.
- Keep externally managed preferences in their existing location; do not copy personal memory or settings into this package. Missing settings do not authorize creating or changing notes.
- A listed sign-in or subscription is a *reported* capability. Verify at run time; never claim access that was not observed.
- Signed-in services authorize reading and searching only — never posting, messaging, reacting, joining, buying, or changing settings. The one exception is NotebookLM when enabled here: the agent may create its own notebooks and add sources, within the limits in notebooklm.md.
- Do not infer the user's profession, discipline, or interests from this file beyond what it states.
