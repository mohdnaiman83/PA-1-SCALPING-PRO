# PA-1 SCALPING PRO

Project Codename: **PHOENIX**

---

# System Architecture

PA-1 SCALPING PRO is a modular Smart Money Concept (SMC) trading engine built using Pine Script v6.

The project is designed around a layered architecture where every module has a single responsibility and communicates only with adjacent layers.

---

# High Level Architecture

```
M01 Core
    │
M02 Environment
    │
M03 Market
    │
M04 HTF
    │
M05 Structure
    │
M06 Liquidity
    │
M07 Premium / Discount
    │
M08 Order Block
    │
M09 Mitigation
    │
M10 Evidence
    │
M11 Trade Qualification
    │
M12 Execution
    │
M13 Risk Management
    │
M14 Dashboard
    │
M15 Renderer
    │
M16 Alert
    │
M17 Trade Manager
```

---

# Layer Definitions

## Foundation Layer

M01

Core configuration

Global variables

Constants

Execution framework

---

## Market Layer

M02

Environment

M03

Market

M04

Higher Timeframe

M05

Structure

M06

Liquidity

M07

Premium / Discount

M08

Order Block

M09

Mitigation

---

## Analysis Layer

M10

Evidence Engine

M11

Trade Qualification

---

## Execution Layer

M12

Execution

M13

Risk Management

---

## Presentation Layer

M14

Dashboard

M15

Renderer

M16

Alert

M17

Trade Manager

---

# Design Principles

- Modular
- Single Responsibility
- Performance First
- Pine Script v6
- Expandable
- Low Coupling
- High Cohesion

---

# Current Version

Baseline Build

v0.6.x

# PHOENIX Architecture

---

## Data Flow

Market Engine
↓
HTF Engine
↓
Structure Engine
↓
Liquidity Engine
↓
Order Block Engine
↓
FVG Engine
↓
Premium / Discount
↓
Evidence Engine
↓
Decision Engine
↓
Trade Manager
↓
Dashboard Data
↓
Dashboard UI
↓
Renderer

---

## Module Ownership

| Module | Owner |
|---------|--------|
| M01 | Core |
| M02 | Config |
| M03 | Market |
| M04 | HTF |
| M05 | Structure |
| M06 | Liquidity |
| M07 | Order Block |
| M08 | FVG |
| M09 | Premium Discount |
| M10 | Session |
| M11 | Risk |
| M12 | Evidence |
| M13 | Dashboard Data |
| M14 | Dashboard UI |
| M15 | Renderer |
| M16 | Alert |
| M17 | Trade Manager |
| M18 | Decision |
| M19 | Utilities |
| M20 | Debug |
| M21 | Performance |
| M22 | Bootstrap |

---

## Ownership Rule

One Module

↓

One Responsibility

↓

One Owner

↓

Many Consumers

Status:

Development
