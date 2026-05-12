# Repository Structure Proposal — Vilnius Travel Guide

### Based on the Customer Journey Map (CJM) Approach

---

## Why Structure Before More Content

The existing site has solid content, but its navigation is organised around **topics** (Guide / Districts / Food & Drink). This is a common starting point, but it forces the user to self-orient — they have to figure out where they are in their own journey and find the right page themselves.

A CJM-based structure reorganises around **the traveller's mental state at each stage**, not around the content categories we happen to have. Pages are ordered by urgency, existing knowledge, stress levels, and next steps.

---

## The Traveller's Journey — Five Stages

| Stage                 | User's mindset         | Primary question             | Reading behaviour  |
| --------------------- | ---------------------- | ---------------------------- | ------------------ |
| **1 · Deciding**      | Curious, uncommitted   | "Is Vilnius worth it?"       | Scanning, skimming |
| **2 · Planning**      | Motivated, needs facts | "What do I need to arrange?" | Reading carefully  |
| **3 · Getting There** | Slightly stressed      | "Am I doing this right?"     | Quick reference    |
| **4 · Exploring**     | Present, time-limited  | "What should I do next?"     | Short bursts       |
| **5 · Going Deeper**  | Comfortable, curious   | "What am I missing?"         | Browsing freely    |

---

## Proposed Repository Structure

```
vilnius-guide/
│
├── docs/
│   │
│   ├── index.md                    ← Hero: Why Vilnius? (Stage 1)
│   │
│   ├── 01-deciding/                ← STAGE 1 · Deciding
│   │   ├── why-vilnius.md          ← "Is it worth the trip?" — the pitch
│   │   ├── best-time.md            ← When to go (already exists, moved here)
│   │   └── how-long.md             ← 2 days vs 4 days: what you can cover
│   │
│   ├── 02-planning/                ← STAGE 2 · Planning
│   │   ├── getting-started.md      ← Visas, entry, currency (already exists)
│   │   ├── budgeting.md            ← Day-by-day cost breakdowns
│   │   ├── where-to-stay.md        ← Neighbourhood guide for accommodation
│   │   └── itineraries/
│   │       ├── 2-day.md            ← Quick visit itinerary
│   │       ├── 4-day.md            ← Full first-visit itinerary
│   │       └── with-kids.md        ← Family-specific itinerary
│   │
│   ├── 03-arriving/                ← STAGE 3 · Getting There & Arriving
│   │   ├── getting-around.md       ← Airport → city, transport (already exists)
│   │   ├── sim-and-connectivity.md ← SIM cards, Wi-Fi, apps (split from getting-started)
│   │   └── safety-and-tips.md      ← What to know on day one
│   │
│   ├── 04-exploring/               ← STAGE 4 · Exploring the City
│   │   ├── districts/
│   │   │   ├── old-town.md         ← (already exists)
│   │   │   ├── uzupis.md           ← (already exists)
│   │   │   └── shnipishkes.md      ← (already exists)
│   │   ├── sights/
│   │   │   ├── top-10.md           ← NEW: scannable "don't miss" reference
│   │   │   └── free-sights.md      ← NEW: budget traveller reference
│   │   ├── food/
│   │   │   ├── cuisine.md          ← (already exists)
│   │   │   ├── restaurants.md      ← (already exists)
│   │   │   └── cafes.md            ← (already exists)
│   │   └── day-trips/
│   │       └── trakai.md           ← NEW: Trakai day trip guide
│   │
│   ├── 05-deeper/                  ← STAGE 5 · Going Deeper
│   │   ├── history.md              ← For those who want context
│   │   ├── language.md             ← More phrases, culture notes
│   │   └── local-life.md           ← Markets, events, living like a local
│   │
│   ├── reference/                  ← Quick-lookup reference (any stage)
│   │   ├── emergency-contacts.md
│   │   ├── useful-apps.md
│   │   └── phrasebook.md
│   │
│   └── about.md                    ← (already exists)
│
├── mkdocs.yml
├── README.md
└── .gitignore
```

---

## How Each CJM Principle Maps to the Structure

### 1 · Pages ordered by urgency and stress level

The `01-deciding → 02-planning → 03-arriving → 04-exploring → 05-deeper` flow mirrors the real emotional arc of a trip. A traveller arriving at the airport does not want the "Why Vilnius?" page — they want `getting-around.md`. The numbered folders make this explicit to both users and contributors.

### 2 · Prerequisites before steps (no hidden blockers)

The existing `getting-started.md` mixes **visa entry** (a blocker, Stage 2) with **SIM cards** (practical on arrival, Stage 3) and **safety tips** (Stage 3). The new structure separates these: blockers live in `02-planning/`, day-one practical info lives in `03-arriving/`. This respects the user's time and prevents the frustration of finding critical information buried mid-page.

### 3 · One document type per page

The CJM material warns against "a single page trying to serve multiple purposes." The proposed structure creates clear genre assignments:

| Page                 | Document type         | Why                                        |
| -------------------- | --------------------- | ------------------------------------------ |
| `why-vilnius.md`     | Pitch / overview      | Scanning reader, uncommitted               |
| `getting-started.md` | Getting-started guide | Motivated reader, needs checklist          |
| `getting-around.md`  | How-to                | Stressed reader, wants steps               |
| `top-10.md`          | Reference             | Time-pressured reader, wants quick answers |
| `history.md`         | Tutorial/explainer    | Comfortable reader, wants depth            |

### 4 · Clear next steps at every stage

Each section folder ends with a natural handoff. A traveller who finishes `02-planning/` is directed to `03-arriving/`; someone exploring `04-exploring/districts/` is prompted to check `04-exploring/food/`. This creates the coherent documentation journey the CJM calls for — individual pages are good, but the overall set must connect.

### 5 · A `reference/` section for any-stage lookups

Reference pages behave differently from journey pages: users jump in from anywhere, scan fast, and leave. Keeping them in a dedicated `reference/` folder prevents them from cluttering the journey flow while making them immediately findable via search.

---

## Summary

The core shift is this: the existing structure asks the user _"what topic are you interested in?"_ The CJM structure asks _"where are you in your journey, and what do you need right now?"_

That single reframe changes how pages are ordered, how they are named, what they include, and how they hand off to each other — which is precisely what the CJM approach is designed to achieve.
