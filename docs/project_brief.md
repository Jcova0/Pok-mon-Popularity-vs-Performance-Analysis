# Project Brief: Pokémon Popularity vs. Performance Analysis

> Template: replace the bracketed placeholders and fill in your own answers.

---

## 1. Project Overview

| Field | Detail |
|---|---|
| **Project name** | Fan Popularity vs. Competitive Performance Analysis |
| **Requestor** | Game Design Lead, *Kanto Interactive* (fictional studio) |
| **Analyst** | Jonathan Covarrubias |
| **Priority** | Medium |
| **Start / target date** | [Start] / [Start + 6 weeks] |
| **Status** | Scoping |

## 2. Background

The design team is planning the next balance patch and a seasonal promotion. Currently, decisions about which Pokémon to buff, feature, or promote rely on opinion. Leadership wants evidence on whether fan popularity and in-game strength are aligned, and where they aren't.

## 3. Business Problem Statement

> *"We don't know which Pokémon are loved but weak (buff candidates), strong but overlooked (promotion candidates), or both loved and strong (safe to feature)."*

## 4. Business Questions

Ranked by priority:

1. Is there a relationship between a Pokémon's popularity and its performance?
2. Which Pokémon have the largest gap between the two?
3. Do attributes like type, generation, or legendary status explain popularity beyond performance?
4. (Stretch) Do TCG card prices track popularity, performance, or neither?

## 5. Objectives and Success Criteria

| Objective | Success looks like |
|---|---|
| Quantify the popularity-performance relationship | A documented metric and a statistical result with stated confidence |
| Identify gap Pokémon | A ranked list of the top and bottom 15 |
| Give actionable recommendations | At least 3 recommendations tied to findings |
| Make results usable | A dashboard the design team can filter without help |

## 6. Scope

**In scope**
- Mainline Pokémon, Gens 1-9
- Competitive singles data
- Popularity from search interest and fan polls

**Out of scope**
- Anime or movie data
- Doubles or VGC formats
- Predicting future popularity
- Individual move or item analysis

## 7. Data Sources

| Source | Content | Grain | Owner / access | Known concerns |
|---|---|---|---|---|
| PokeAPI | Stats, types, generation | One row per Pokémon | Public API | Forms and variants |
| Smogon stats | Usage rates | Pokémon × tier × month | Public files | Format changes over time |
| Google Trends | Search interest | Term × week | pytrends | Relative, not absolute, values |
| Fan polls | Popularity ranks | Pokémon | Public polls | Gen 1 and self-selection bias |
| TCG API *(stretch)* | Card prices | Card | Public API | Price volatility |

## 8. Requirements

**Data requirements**
- [ ] Raw data preserved unaltered
- [ ] A documented mapping for name mismatches across sources
- [ ] Defined handling of regional forms and alternate forms

**Analytical requirements**
- [ ] Metrics defined and documented (popularity index, performance index)
- [ ] Methodology appropriate for skewed data
- [ ] Limitations and bias section

**Reporting requirements**
- [ ] Executive summary (1 page, non-technical)
- [ ] Interactive dashboard with generation/type filters
- [ ] Technical documentation to reproduce the analysis

## 9. Deliverables

| # | Deliverable | Audience | Format |
|---|---|---|---|
| 1 | Project brief and data dictionary | Team | Markdown / doc |
| 2 | Clean, documented dataset | Analysts | Database / CSVs |
| 3 | Analysis notebooks | Analysts | Jupyter |
| 4 | Dashboard | Design team | Tableau / Power BI |
| 5 | Executive summary with recommendations | Leadership | 1-page PDF |

## 10. Assumptions and Risks

| Risk / assumption | Impact | Mitigation |
|---|---|---|
| Names don't match across sources | Lost or wrong joins | Build a mapping table, report the match rate |
| Popularity data is biased | Misleading conclusions | Use multiple sources and state limitations |
| Scope creep | Missed deadline | Keep the stretch goals optional |
| API limits | Delays | Cache raw responses |

## 11. Work Breakdown

**Epic 1: Setup and Scoping** (Week 1)
- [ ] Write project brief and finalize questions
- [ ] Create repo and folder structure
- [ ] Start data dictionary

**Epic 2: Data Collection** (Week 2)
- [ ] Ingest PokeAPI
- [ ] Ingest Smogon usage
- [ ] Ingest Google Trends
- [ ] Ingest fan poll data

**Epic 3: Cleaning and Modeling** (Week 3)
- [ ] Build name-mapping table
- [ ] Resolve forms and variants
- [ ] Run data quality checks
- [ ] Load to database with schema

**Epic 4: Analysis** (Week 4)
- [ ] Define popularity and performance metrics
- [ ] Exploratory analysis
- [ ] Statistical testing
- [ ] Gap/residual analysis

**Epic 5: Reporting** (Week 5)
- [ ] Build dashboard
- [ ] Write executive summary
- [ ] Document limitations

**Epic 6: Review and Handoff** (Week 6)
- [ ] Peer or self-review against requirements
- [ ] Finalize README
- [ ] Present findings

## 12. Milestones and Check-ins

| Date | Milestone |
|---|---|
| End of Week 1 | Brief approved |
| End of Week 3 | Clean data ready |
| End of Week 5 | Draft dashboard and findings |
| End of Week 6 | Final presentation |

## 13. Repo Structure

```
pokemon-popularity-vs-performance/
├── README.md              <- summary and how to reproduce
├── docs/
│   ├── project_brief.md
│   ├── data_dictionary.md
│   └── data_quality_log.md
├── data/
│   ├── raw/
│   └── clean/
├── sql/
├── notebooks/
│   ├── 01_collect.ipynb
│   ├── 02_clean.ipynb
│   ├── 03_explore.ipynb
│   └── 04_analyze.ipynb
├── dashboard/
└── reports/
    └── executive_summary.pdf
```
