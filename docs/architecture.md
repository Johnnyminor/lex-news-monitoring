# Architecture

## Overview

The application follows a pipeline design: news is collected, processed,
stored, and served. Each stage lives in its own module under `src/`, keeping
collectors, business logic, and delivery independent.

## Components

### Collectors (`src/collectors/`)

One module per source type (RSS feed, REST API, HTML page). Each collector is
responsible for:

- Fetching articles on a schedule
- Normalizing them into a common article format (title, body, URL, published
  date, source)
- Handing them to the processing stage

### Processing (`src/processing/`)

- **Deduplication:** identify reprints and syndicated copies of the same story.
- **Matching:** score articles against Lex.dk topics using keyword lists and,
  later, NLP/semantic matching.
- **Classification:** tag articles by legal area (e.g. criminal law, family
  law, EU law).

### Storage (`src/storage/`)

Persistent store for articles, source metadata, match results, and editorial
review status. Exact database technology TBD (a relational DB is the working
assumption).

### API (`src/api/`)

Internal REST API used by the editorial UI to browse matches, filter by topic
or source, and mark articles as reviewed.

### Notifications (`src/notifications/`)

- Daily digest email summarizing new relevant articles
- Immediate alerts for high-priority matches

### Configuration (`src/config/`)

Source registry (which feeds to monitor, polling intervals) and runtime
settings, loaded from environment variables where possible.

## Open Design Questions

- Choice of implementation language and framework
- Database choice and schema
- Whether the editorial interface is a standalone web UI or built on the API
- Matching strategy: keyword-only first, semantic later?
