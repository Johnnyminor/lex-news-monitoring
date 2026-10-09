# News Monitoring App for Lex.dk

A news monitoring application that tracks Danish news sources and flags
articles relevant to [Lex.dk](https://lex.dk) — the Danish national legal
encyclopedia — so editors can discover developments in law and jurisprudence
that may require new or updated encyclopedia entries.

## Purpose

Lex.dk covers Danish law, and legal landscapes change constantly: new
legislation, landmark rulings, political initiatives, and public debates all
affect the accuracy of existing entries. Monitoring these developments by hand
is time-consuming. This app automates the collection, filtering, and triage of
news coverage so the editorial team can focus on writing, not searching.

## How It Works

```
News sources (RSS, APIs, sites)
        │
        ▼
 Collectors ── fetch & normalize articles
        │
        ▼
 Processing ── deduplicate, keyword/NLP matching,
        │         relevance scoring against Lex.dk topics
        ▼
 Storage ──── persist articles, matches, review status
        │
        ├──► API ──────── browse & manage flagged articles
        └──► Notifications ── daily digests & instant alerts
```

## Project Structure

```
lex-news-monitoring/
├── docs/                 # Architecture, roadmap, and design notes
├── src/
│   ├── collectors/       # Per-source scrapers and API/RSS clients
│   ├── processing/       # Matching, deduplication, relevance scoring
│   ├── storage/          # Database models and data access
│   ├── api/              # REST API for browsing/managing matches
│   ├── notifications/    # Email digests and real-time alerts
│   └── config/           # App configuration and source definitions
├── tests/
│   ├── unit/
│   └── integration/
├── scripts/              # Operational and data-setup scripts
├── infra/                # Deployment manifests (Docker, CI, etc.)
└── data/                 # Local data directory (gitignored)
```

## Getting Started

The project is currently in the scaffolding phase — folder structure and
documentation are in place, implementation starts in the `src/` modules above.

1. Clone the repository.
2. Review `docs/architecture.md` for the system design.
3. Check `docs/roadmap.md` for planned milestones and current status.

## Data Sources (planned)

- Danish news media RSS feeds and public APIs
- Court decisions and press releases from legal institutions
- Official legislative channels (Folketinget, retsinformation.dk)

## License

To be determined.
