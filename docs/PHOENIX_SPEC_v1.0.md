# PA-1 SCALPING PRO
## PHOENIX Architecture Specification
### Version 1.0
### Status: Official Master Document

> Engine Thinks. Trader Executes.

---

# 1. Project Overview

PA-1 SCALPING PRO (Project Codename: PHOENIX) is a professional Smart Money Concept (SMC) trading framework developed in Pine Script v6.

Unlike a traditional indicator, PHOENIX is designed as a modular decision engine where every module has a single responsibility and every piece of data has a single owner.

Primary Market

- FCPO
- Gold (XAUUSD)
- Expandable to other instruments

---

# 2. Project Vision

Create a professional-grade trading framework that is:

- Modular
- Scalable
- Maintainable
- High Performance
- Easy to Audit
- Easy to Extend

Core Philosophy

> Engine Thinks. Trader Executes.

---

# 3. Core Design Principles

## Principle 1

Single Source of Truth

Every data element has exactly one owner.

No duplicate ownership.

---

## Principle 2

One Module = One Responsibility

Every module performs one task only.

---

## Principle 3

Read > Modify

Downstream modules may read upstream data.

They must never overwrite it.

---

## Principle 4

Predictability

Every execution path must produce deterministic results.

---

## Principle 5

Performance First

Avoid unnecessary calculations.

Avoid object recreation.

Avoid duplicated logic.

---

# 4. System Architecture

Session Engine

↓

Market Engine

↓

HTF Engine

↓

Structure Engine

↓

Liquidity Engine

↓

Premium / Discount Engine

↓

Order Block Engine

↓

Mitigation Engine

↓

Evidence Engine

↓

Qualification Engine

↓

Execution Engine

↓

Risk Engine

↓

Decision Engine

↓

Trade Manager

↓

Trading State Recorder (Future)

↓

Dashboard

↓

Renderer

↓

Alert Engine

---

# 5. Module Specification

| Module | Description |
|---------|-------------|
| M01 | Core Framework |
| M02 | Session Engine |
| M03 | Market Engine |
| M04 | HTF Engine |
| M05 | Structure Engine |
| M06 | Liquidity Engine |
| M07 | Premium / Discount |
| M08 | Order Block |
| M09 | Mitigation |
| M10 | Evidence |
| M11 | Qualification |
| M12 | Execution |
| M13 | Risk Management |
| M14 | Dashboard |
| M15 | Renderer |
| M16 | Alert |
| M17 | Trade Manager |
| M18 | Decision Engine |
| M19 | Validation |
| M20 | Lifecycle |
| M21 | Performance |
| M22 | Signal Quality |
| M23 | Audit & Refactoring |
| M24 | Trading State Recorder |

---

# 6. Data Ownership Matrix

| Data | Owner |
|------|-------|
| Session | M02 |
| Trend | M03 |
| HTF Bias | M04 |
| Structure | M05 |
| Liquidity | M06 |
| Premium/Discount | M07 |
| Order Block | M08 |
| Mitigation | M09 |
| Evidence | M10 |
| Qualification | M11 |
| Signal | M18 |
| Entry | M13 |
| Stop Loss | M13 |
| Take Profit | M13 |
| Trade State | M17 |
| Dashboard | M14 |
| Rendering | M15 |
| Alerts | M16 |
| Performance | M21 |
| Trade History | M24 |

---

# 7. State Machine

WAIT

↓

READY

↓

ENTRY

↓

ACTIVE

↓

BREAK EVEN

↓

PARTIAL

↓

TP

↓

SL

↓

CLOSED

Trade Manager is the only owner of this state machine.

---

# 8. Naming Convention

Global Variables

g_

Engine Variables

e_

Risk Management

rm_

Lifecycle

lc_

Dashboard

db_

Trading State Recorder

tsr_

Performance

pf_

Configuration

cfg_

Constants

CONST_

---

# 9. Coding Standards

Mandatory Rules

- No duplicated ownership
- No magic numbers
- Use enums whenever possible
- No duplicated calculations
- No duplicated dashboards
- No duplicated state machines
- One owner per variable
- All constants centralized
- Modular architecture only

---

# 10. Development Workflow

Feature

↓

Development

↓

Internal Test

↓

Audit

↓

Regression Test

↓

Baseline Freeze

↓

Release

---

# 11. Branch Strategy

main

Stable Release

develop

Active Development

feature/*

New Features

hotfix/*

Critical Fixes

release/*

Release Preparation

---

# 12. Versioning

v0.1.x

Foundation

v0.2.x

Trading State Recorder

v0.3.x

Historical Database

v0.4.x

Performance Analytics

v0.5.x

Replay Engine

v1.0.0

Production Ready

---

# 13. Current Project Status

Current Branch

develop

Current Stage

M23

Current Baseline

v0.6.x

Architecture

Stable

Audit

Completed

Critical Fixes

Pending

Regression

Pending

---

# 14. Known Architecture Rules

✔ Single Source of Truth

✔ One Module One Responsibility

✔ Read Only Downstream

✔ Event Driven Design

✔ Layered Architecture

✔ Modular Development

✔ High Cohesion

✔ Low Coupling

---

# 15. Development Roadmap

Completed

- Core Framework
- Session
- Market
- HTF
- Structure
- Liquidity
- PD
- OB
- Mitigation
- Evidence
- Qualification
- Execution
- Risk
- Dashboard
- Renderer
- Alert
- Trade Manager
- Validation
- Lifecycle
- Performance
- Signal Quality
- Audit

Next

M24

Trading State Recorder

↓

M25

Historical Database

↓

M26

Performance Analytics

↓

M27

Replay Engine

↓

M28

AI Decision Optimizer

---

# 16. Documentation

Official Documents

- README.md
- PHOENIX_SPEC_v1.0.md
- CHANGELOG.md
- KNOWN_ISSUES.md
- RELEASE_NOTES.md
- BASELINE_AUDIT.md

---

# 17. License

Copyright © PA-1 Project

Project Codename

PHOENIX 🔥

All Rights Reserved.

---

# 18. Closing Statement

PHOENIX is engineered as a professional trading framework rather than a conventional TradingView indicator.

Every architectural decision follows software engineering principles emphasizing maintainability, scalability, deterministic behavior, modularity, and long-term extensibility.

> Engine Thinks. Trader Executes.

---
