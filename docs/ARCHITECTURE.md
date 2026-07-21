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

21/7/26
# PA-023 --- Developer Diagnostic System (DDS)

**Status:** LOCKED\
**Project:** PA-1 SCALPING PRO (PHOENIX)

------------------------------------------------------------------------

# Objective

Create a **read-only diagnostic subsystem** for PA-1 that provides full
engine visibility for development, validation and troubleshooting
without affecting trading logic.

> Philosophy:
>
> **"Don't guess the problem. Follow the data until the point where it
> stops."**

------------------------------------------------------------------------

# Core Principles

-   Read Only
-   Zero Side Effect
-   Pine First Design
-   Live Diagnostics
-   Root Cause Analysis
-   Data Logger
-   Circular History (Flight Recorder)
-   Variable Watch
-   Module Health
-   Pipeline Trace
-   Delta Logging

------------------------------------------------------------------------

# High-Level Architecture

``` text
                 PA-1 ENGINE (M01-M22)
                         │
          ┌──────────────┴──────────────┐
          │                             │
          ▼                             ▼

   Trading Output                Diagnostic Output
          │                             │
          ▼                             ▼

 Trading Dashboard          PA-023 DDS (Read Only)
```

------------------------------------------------------------------------

# DDS Components

## Phase 1

-   Live Monitor
-   Module Status
-   Root Cause
-   Pipeline Trace
-   Variable Watch
-   Engine Health

## Phase 2

-   Data Logger
-   Circular History
-   Timeline
-   Event Log
-   Module Inspector

## Phase 3

-   Performance Statistics
-   Execution Counter
-   Dependency Viewer
-   Module Version Tracking

------------------------------------------------------------------------

# Data Logger

Each log entry should contain:

-   Timestamp
-   Bar Index
-   Module
-   Status
-   Reason
-   Key Variables
-   Execution Time

Prefer **delta logging** (only log changes) to reduce memory usage.

------------------------------------------------------------------------

# Flight Recorder

Implement as a circular buffer.

Suggested capacity: - 50 - 100 - 200 events

Oldest records are overwritten automatically.

------------------------------------------------------------------------

# Root Cause Analysis

DDS should identify:

-   Blocking Module
-   Blocking Rule
-   Failure Reason
-   Upstream Dependency

Example:

NO TRADE → M14 Mandatory Gate → Liquidity Missing → Source: M04
Liquidity Engine

------------------------------------------------------------------------

# Module Diagnostic Contract

Every module (M01-M22) should expose:

-   Module Name
-   Version
-   Triggered
-   Status
-   Reason
-   Inputs
-   Outputs
-   Key Variables
-   Execution Counter
-   Execution Time
-   Dependencies

DDS only reads these values.

------------------------------------------------------------------------

# Pine Script Constraints

Supported: - Tables - Arrays - Circular buffers - Read-only inspection -
Timeline - Variable watch - Root cause - Pipeline trace

Not in scope: - Unlimited history - Persistent database - Desktop-style
clickable UI - External storage

------------------------------------------------------------------------

# Final Design Lock

DDS is a developer subsystem only.

It shall never:

-   Generate trading signals
-   Modify engine variables
-   Change BUY/SELL decisions
-   Affect risk management
-   Affect dashboard logic

Its only purpose is to inspect, validate and troubleshoot the PA-1
Engine.

**Architecture Status:** LOCKED

