# Holistis — AI health platform, built by one person

> Live at **[longevityai.nl](https://longevityai.nl)** — Dutch market, fully compliant, fully autonomous.

**Who uses it:**
- People with chronic symptoms but no clear diagnosis (fatigue, hormonal, gut, etc.)
- HR teams running employee wellness checks at scale
- Holistic practitioners who want their own client portal

Currently live and in active development. ~149,000 lines of code. Built solo.

---

## Autonomous systems running 24/7

I don't manually write blog posts, monitor the app, or push hotfixes at 2am. Five systems handle that — and one of them makes the AI smarter every week without me touching it.

**Nightly QA + auto-fix loop** — 130 Playwright tests run against the live app every night. When something breaks, Claude Code automatically writes a fix, opens a PR, and merges it when CI passes. I get one weekly email. Zero-maintenance production monitoring for a one-person team.

**Autonomous marketing machine** — Every 6 hours: BBC Health, PubMed, EFSA and ClinicalTrials are scanned for relevant publications. Matching items are automatically turned into trilingual (NL/EN/FR) blog posts — EFSA-checked claims, internal links, AI-generated cover images — and published directly to longevityai.nl/blog. No editor needed.

**AI video pipeline** — Health topics are turned into short-form social videos via Heygen (AI presenter) + fal.ai (Veo/Sora) and distributed across platforms. The whole pipeline from topic to published video runs without manual intervention.

**Self-improving AI brain** — This is the one that's different:

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
  ├── Static relevance filter (playwright, ai, health, automation, ...)
  └── Haiku summary → admin UI

Every Monday 07:00
  Weekly digest → my inbox
  ├── What did the system learn this week?
  ├── Synthetic loop results (gaps, legal flags)
  └── Auto-processed PubMed papers

Agent Orchestrator (always active)
  └── Receives events from all agents → triggers downstream actions
```

Every report generated after Wednesday is smarter than the one from the week before — through what the synthetic patients found, converted into knowledge base facts without a single manual step. Cost: max €0.60/week.

**Compliance scan** — A `compliance.spec.ts` Playwright spec scans the live site nightly for forbidden medical language (cure claims, stop-medication advice) via the same regex patterns as the server-side filter. Two independent checkpoints, €0 in tokens.

---

## Psychological profiling — €0 extra

Every report detects the patient's psychological archetype from existing intake answers (no new questions, no extra LLM call) and adapts tone accordingly:

| Archetype | Approach |
|---|---|
| Overwhelmed | Deep validation first, tiny steps, no bullet-point walls |
| Skeptical | Biological mechanism before the recommendation |
| Ready but scared | Week 1 as simple as possible, explicit success markers |
| Knowledge-seeker | Enzymes and neurotransmitters before the advice |
| Beginner | Warm, simple, reassuring |

---

## Open source tools I've built

**[claude-memory-trim](https://github.com/holistis/claude-memory-trim)** — keeps Claude Code's context window lean by automatically rotating session logs between hot and cold storage. Cuts token cost at session start by 60-80%. 99 lines of vanilla Node.js.

**[muraqib](https://github.com/holistis/muraqib)** — a nightly QA guardian for solo SaaS founders. 130 Playwright tests run against your live app every night. When something breaks, Claude Code automatically writes a fix, opens a PR, and merges it when CI passes. You get one weekly email. Zero-maintenance production monitoring for one-person teams.

---

## Tech stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![React 18](https://img.shields.io/badge/React_18-61DAFB?style=flat&logo=react&logoColor=black)
![Node.js 22](https://img.shields.io/badge/Node.js_22-339933?style=flat&logo=nodedotjs&logoColor=white)
![tRPC](https://img.shields.io/badge/tRPC-2596BE?style=flat&logo=trpc&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![MySQL 9](https://img.shields.io/badge/MySQL_9-4479A1?style=flat&logo=mysql&logoColor=white)
![Drizzle ORM](https://img.shields.io/badge/Drizzle-C5F74F?style=flat&logo=drizzle&logoColor=black)
![Claude API](https://img.shields.io/badge/Claude_API-D97706?style=flat)
![Stripe](https://img.shields.io/badge/Stripe-008CDD?style=flat&logo=stripe&logoColor=white)

---

## Compliance

Built for the Dutch market:
- **GDPR/AVG** — DPIA completed, pseudonymization enforced on every LLM call
- **IGJ** — Lifestyle coach positioning, no MDR classification, EFSA-verified claims only
- **Wet BIG** — No diagnosis, no treatment advice, legal disclaimer in every report
- **BOIP i-DEPOT** — Concept + methodology registered (nr. 159999, May 2026)

---

## If you're a developer reading this

The codebase is proprietary. But if you're building something in health AI, compliance-heavy SaaS, or autonomous systems — I'm open to a conversation.

📧 [info@holistischadviseur.nl](mailto:info@holistischadviseur.nl)
🌐 [longevityai.nl](https://longevityai.nl)
