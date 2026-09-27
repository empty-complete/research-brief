# User profile (optional — fill in to personalize)

This file is the only place for personal preferences. The rest of the skill is generic. If this file is empty or left as the template, the agent uses the defaults in the right column. Keep secrets out of it: never put passwords, API keys, cookies, or tokens here.

| Setting | Your value | Default if empty |
| --- | --- | --- |
| Output language | | Language of the user's request |
| Extra search languages (always try) | | Chosen per topic (English + the user's language + topic-relevant ones) |
| Default depth tier | | Standard |
| Mandatory channels (always attempt) | | Reddit, YouTube |
| Extra channels for broad research | | TikTok, Instagram, Facebook, forums, image search, Telegram (when topic fits) |
| Excluded sources | | None |
| Preferred general search engine | | Whatever search tool is available; optionally DuckDuckGo `kl=wt-wt` via browser |
| Signed-in services the agent may read with (browser) | | None assumed; discover at run time |
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
Institutional access: university network — ScienceDirect, Springer (via browser session)
Country for prices/availability: Germany
```

## Rules for using this profile

- Preferences here are defaults; the current request always wins.
- A listed sign-in or subscription is a *reported* capability. Verify at run time; never claim access that was not observed.
- Signed-in services authorize reading and searching only — never posting, messaging, reacting, joining, buying, or changing settings.
- Do not infer the user's profession, discipline, or interests from this file beyond what it states.
