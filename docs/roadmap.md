# Roadmap

## Milestone 0 — Scaffolding (current)

- [x] Repository structure
- [x] README and architecture documentation
- [ ] Choose implementation language and framework

## Milestone 1 — MVP: manual-feed monitoring

- [ ] RSS collector for a small set of Danish news sources
- [ ] Keyword-based matching against a curated Lex.dk topic list
- [ ] Basic storage of articles and matches
- [ ] Daily digest email to the editorial team

## Milestone 2 — Editorial workflow

- [ ] REST API for browsing matches
- [ ] Review workflow (mark as relevant/irrelevant, assign to editor)
- [ ] Additional collectors (APIs, institutional sources)

## Milestone 3 — Smarter matching

- [ ] Deduplication of syndicated stories
- [ ] Semantic/NLP-based relevance scoring
- [ ] Classification by legal area
- [ ] Dashboard with statistics

## Milestone 4 — Operations

- [ ] Dockerized deployment
- [ ] CI pipeline (lint, test, build)
- [ ] Monitoring and alerting on collector failures
