# Scalar

[![CI](https://github.com/fahrizzdev/ApexMath/actions/workflows/ci.yml/badge.svg)](https://github.com/fahrizzdev/ApexMath/actions/workflows/ci.yml)
![Node.js](https://img.shields.io/badge/Node.js-20%2B-339933?logo=nodedotjs&logoColor=white)
![Status](https://img.shields.io/badge/status-active%20prototype-2563eb)

Adaptive math learning from arithmetic through Calculus II.

Scalar starts with a diagnostic, adjusts question difficulty as a learner progresses, and turns performance into a focused study loop: lessons, weak-topic tracking, daily practice, notes, and study history.

## What it does

- **Adaptive placement** across 7 levels, from Arithmetic to Calculus II
- **93 structured lessons** with explanations, worked examples, practice, and quick checks
- **Topic-level mastery tracking** that surfaces weak areas and links them back to lessons
- **Daily quizzes** weighted toward topics a learner is missing
- **Progress dashboard** with streaks, recent quiz performance, weak topics, and study time
- **Accounts + persistence** for progress, notes, diagnostic results, and study sessions
- **Multiple visual themes** and KaTeX-rendered math

## Stack

- Vanilla HTML, CSS, and JavaScript
- Node.js + Express
- PostgreSQL
- KaTeX

## Architecture

```text
Browser
  ├─ adaptive diagnostic
  ├─ lessons + practice
  ├─ dashboard / notes / study timer
  │
  ▼
Express API
  ├─ auth
  ├─ adaptive question sessions
  ├─ topic-performance tracking
  └─ daily quiz + progress endpoints
  │
  ▼
PostgreSQL
```

The question bank is organized into seven difficulty bands and tagged by topic. Diagnostic sessions persist the questions already seen and adjust the current level from performance. Logged-in users also persist topic accuracy, quiz results, notes, streaks, and study sessions.

## Run locally

Requirements: Node.js 20+ and PostgreSQL.

```bash
npm install
cp .env.example .env
npm start
```

Open `http://localhost:3000`.

Run the current validation suite with:

```bash
npm test
```

## Repository map

```text
index.html      main application + diagnostic/dashboard UI
lessons.html    lesson library and practice experience
questions.js    leveled, topic-tagged question bank
server.js       Express API, auth, adaptation, and persistence
package.json    runtime dependencies and scripts
```

## Roadmap

- Expand automated coverage beyond syntax validation
- Harden authentication and input validation
- Add reproducible database migrations and seed data
- Publish a stable hosted demo
- Improve accessibility and mobile behavior

## Status

Active prototype. The core adaptive learning loop, persistence layer, and lesson system are implemented; lesson coverage and learning logic are continuing to evolve.

Contributions and responsible security reports are welcome—see [CONTRIBUTING.md](CONTRIBUTING.md) and [SECURITY.md](SECURITY.md).
