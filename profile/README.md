# Holistis — AI health platform, built by one person

> Live at **[longevityai.nl](https://longevityai.nl)** — Dutch market, fully compliant, fully autonomous.

---

## What I built

A full-stack longevity platform that generates a personalized 6-month lifestyle plan in 5-15 minutes. 28-question intake, pattern recognition across 10+ organ systems, trilingual (NL/EN/FR), GDPR + Dutch medical law compliant.

Solo-built. In production. Self-improving.

---

## The system that runs while I sleep

This isn't just a product with automated tests. It's a platform with a **self-improving AI brain**:

```
Every Wednesday 03:00
  Synthetic Patients Agent
  ├── 10 fake patient profiles (5 conditions × 2 archetypes)
  ├── Runs real reports through the production pipeline
  ├── Haiku agent scores on 4 dimensions
  │   (protocol depth / personalization / supplement specificity / legal safety)
  ├── Gaps → knowledge base proposals
  └── Legal flag → triggers compliance agent immediately

Every Wednesday 04:00
  Auto-KB Agent
  ├── PubMed papers (free API) → fetch abstracts
  ├── Haiku extracts 3-5 core facts per paper
  └── Facts → knowledge_triples → next report is smarter

Every Tuesday 03:30
  Developer Tools Radar
  ├── GitHub Trending + dev.to scanned weekly
  ├── Static relevance filter
  └── Haiku summary → admin UI

Every Monday 07:00
  Weekly digest → my inbox
  ├── What did the system learn this week?
  ├── Synthetic loop results (gaps, legal flags)
  ├── Auto-processed PubMed papers
  └── Dev tools on the radar

Agent Orchestrator (always active)
  └── Receives events from all agents → triggers downstream actions
```

**In practice:** every report generated after Wednesday is smarter than the one from the week before — automatically, without a single manual step.

**Cost of the learning loop:** max ~€0.60/week.

---

## Psychological profiling — €0 extra

Every report detects the patient's psychological archetype from existing intake answers (no new questions, no LLM call) and adapts tone accordingly:

| Archetype | Approach |
|---|---|
| Overwhelmed | Deep validation first, tiny steps, no bullet-point walls |
| Skeptical | Biological mechanism before the recommendation |
| Ready but scared | Week 1 as simple as possible, explicit success markers |
| Knowledge-seeker | Enzymes and neurotransmitters before the advice |
| Beginner | Warm, simple, reassuring |

---

## Muraqib — 130-test nightly QA + AI auto-fix

```
Every night 02:00 UTC
      ↓
130 Playwright tests on longevityai.nl
(SEO, auth flows, blog, intake,
 AI Coach, compliance scan, payments)
      ↓
Tests fail?
      ↓
Claude Code GitHub App analyzes failures
      ↓
Fix PR created → CI green → auto-merge
```

Includes a `compliance.spec.ts` that scans the live site for forbidden medical language via the same regex patterns as the server filter. Two independent checkpoints, €0 in tokens.

---

## Stack

| Layer | Choice |
|---|---|
| Frontend | React 18 + Vite + TypeScript + TailwindCSS |
| Backend | tRPC + Express + Node.js 22 |
| Database | MySQL 9 via Drizzle ORM (Railway) |
| Auth | Clerk (MFA, trilingual) |
| Payments | Stripe Checkout + Connect |
| AI | OpenAI GPT-4o + Claude Sonnet + Flux for images |
| Email | Brevo |
| Hosting | Railway (auto-deploy) |
| QA | 130 Playwright tests, nightly, AI-powered auto-fix |

---

## Compliance

Built for the Dutch market with a full compliance stack:
- **GDPR/AVG** — DPIA completed, pseudonymization enforced on every LLM call
- **IGJ** — Lifestyle coach positioning, no MDR classification, EFSA-verified claims
- **Wet BIG** — No diagnosis, no treatment advice, legal disclaimer in every report
- **BOIP i-DEPOT** — Concept + methodology registered (nr. 159999, May 2026)

---

## If you're a developer reading this

The codebase is proprietary. But if you're building something in health AI, compliance-heavy SaaS, or autonomous systems — I'm open to a conversation.

📧 [info@holistischadviseur.nl](mailto:info@holistischadviseur.nl)
🌐 [longevityai.nl](https://longevityai.nl)
