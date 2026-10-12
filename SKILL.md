---
name: seo-aeo-daily-digest
description: Research the last 24 hours of SEO, AEO (answer engine optimization) and GEO (generative engine optimization) news — Google/Bing algorithm and core updates, AI Overviews / AI Mode, ChatGPT / Perplexity / Copilot / Gemini search changes, crawler and robots policy, structured data, ranking volatility — and email a prioritized digest via Outlook. Use when asked for the SEO/AEO/GEO news digest, or when the daily routine fires.
---

# SEO / AEO / GEO Daily Digest

Produce one email per day telling the reader what changed in search and AI-answer
visibility, why it matters, and what (if anything) to do about it.

- **Recipient:** <your-email@example.com>  (replace with the digest recipient)
- **Window:** news published in the last ~30 hours (a little overlap so nothing
  slips between runs). Today's date comes from the environment.
- **Always send**, even on quiet days (a short "no major changes" note proves the
  routine ran).

## 1. Check what was already reported

Use `outlook_email_search` with `query: "SEO/AEO/GEO Daily Digest"` and
`afterDateTime: "3 days ago"`. Read the most recent one or two digests (via
`read_resource`). Do not repeat an item already covered unless there is a material
new development (e.g. a rollout that was "started" is now "complete", new data on
impact, Google clarified something). Label those as **Update:**.

## 2. Research (cast a wide net, then filter)

Run searches in parallel. Prefer primary sources; use trade press to find and
contextualize them. Verify dates — only include items actually published or
changed inside the window.

**Primary / official sources (check every run):**
- Google Search Status Dashboard — https://status.search.google.com/ (ranking
  incidents: core, spam, reviews, site-reputation-abuse updates; start/complete)
- Google Search Central Blog — https://developers.google.com/search/blog
- Google Search documentation updates log —
  https://developers.google.com/search/updates
- Google "The Keyword" blog (Search, AI Overviews, AI Mode, Discover)
- Bing Webmaster Blog — https://blogs.bing.com/webmaster ; IndexNow news
- OpenAI news (ChatGPT search, OAI-SearchBot/GPTBot, shopping, ads in answers)
- Perplexity blog / changelog; Microsoft Copilot; Anthropic (Claude web search,
  ClaudeBot); Apple (Siri/Safari search); Meta AI; Gemini app

**Trade press & trackers:**
- Search Engine Roundtable (seroundtable.com) — fastest on unconfirmed updates
- Search Engine Land, Search Engine Journal
- Volatility sensors: Semrush Sensor, MozCast, SimilarWeb, Advanced Web Ranking,
  Accuranker grump, CognitiveSEO Signals (report notable spikes, not noise)
- Analyses from Ahrefs, Semrush, Moz, Sistrix, BrightEdge, seoClarity, Similarweb
  on AI Overviews / AI Mode / zero-click / referral traffic from LLMs

**Suggested search queries (adapt to the date):**
- "Google core update" / "spam update" / "algorithm update" <month year>
- "Google Search Status Dashboard" ranking incident
- "AI Overviews" OR "AI Mode" change / expansion / rollout
- "Search Console" new feature / report / bug
- ChatGPT search / Perplexity / Copilot / Gemini citations sources update
- GEO OR "generative engine optimization" OR "AI search visibility" study
- robots.txt OR llms.txt OR "Google-Extended" OR GPTBot OR crawler policy
- schema.org OR "structured data" OR "rich results" deprecated / new
- Google antitrust remedies search; EU DMA search; publisher licensing AI
- "Danny Sullivan" OR "Search Liaison" OR "John Mueller" said

## 3. What counts (and what doesn't)

Include, ranked by impact:
1. **Algorithm & ranking updates** — confirmed (Google/Bing) and strong
   unconfirmed volatility with corroboration from multiple trackers/forums.
2. **AI answer surfaces** — AI Overviews, AI Mode, ChatGPT search, Perplexity,
   Copilot, Gemini, Claude: launches, expansions to new markets/languages,
   citation/link display changes, ads in AI answers, referral-traffic changes.
3. **Crawling, indexing & access** — Googlebot/Bingbot behavior, AI crawler user
   agents, robots.txt / llms.txt developments, IndexNow, rendering.
4. **SERP features & Search Console / Bing Webmaster Tools** — feature
   added/removed, reporting changes, data bugs or lags.
5. **Structured data & documentation** — new/deprecated rich results, guideline
   or spam-policy wording changes.
6. **Policy, legal & industry** — antitrust remedies, regulation, publisher
   deals, major studies with real data on AEO/GEO.

Skip: generic how-to listicles, opinion pieces with no news, vendor marketing,
rumor from a single unverified source (or include it clearly marked
**Unconfirmed**).

## 4. Write the email

Send with `outlook_send_mail`, `bodyType: "html"` (allowed tags: headings,
paragraphs, links, lists, basic formatting, tables — no `<style>`, `<span>`,
`<img>`).

**Subject:** `SEO/AEO/GEO Daily Digest — <Mon DD, YYYY>` and, if something is
big, append ` — <headline>` (e.g. `— Google October 2026 core update rolling out`).

**Body structure:**

```
<h2>TL;DR</h2>
<ul> 2–4 bullets: the things that matter most today </ul>

<h2>🔴 Algorithm & Ranking Updates</h2>
<h2>🤖 AI Search / AEO / GEO</h2>
<h2>🕷️ Crawling, Indexing & Bots</h2>
<h2>🔎 SERP Features, Search Console & Tools</h2>
<h2>📜 Structured Data, Docs & Policies</h2>
<h2>⚖️ Industry, Legal & Research</h2>

<h2>✅ Action items</h2>
<ul> concrete things to check or do this week (e.g. annotate GA4/GSC with the
update start date, watch rankings for X, update robots.txt for new bot Y) </ul>

<h2>📈 Volatility snapshot</h2>
<p> one line: current read of Semrush Sensor / MozCast etc. if available </p>
```

Each item: **bold headline** — 1–3 sentences on what changed and why it matters
for SEO/AEO/GEO — status tag (**Confirmed** / **Unconfirmed** / **Update:**) —
source link(s), primary source first. Omit empty sections. Keep it skimmable:
aim for under ~600 words unless it is a major update day.

**Quiet day:** send a short email with subject
`SEO/AEO/GEO Daily Digest — <date> — No major changes`, a one-line summary,
any minor items worth a glance, and the volatility snapshot.

## 5. Finish

After sending, reply with a 2–3 line summary of what was emailed (headline items
and count). If sending fails, retry once; if it still fails, put the full digest
in the final reply so it is not lost.
