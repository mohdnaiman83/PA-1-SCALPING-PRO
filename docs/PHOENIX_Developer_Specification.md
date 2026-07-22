# PA-1 SCALPING PRO

## Project Codename: PHOENIX

### Developer Specification v1.0

**Status:** LOCKED

------------------------------------------------------------------------

# Architecture (Frozen)

## Foundation

-   M01 Core
-   M02 Environment
-   M03 Market
-   M04 HTF

## Analysis

-   M05 Structure
-   M06 Liquidity
-   M07 Premium/Discount
-   M08 Order Block
-   M09 Mitigation
-   M10 Evidence
-   M11 Qualification
-   M12 Execution
-   M13 Risk

## Presentation

-   M14 Dashboard
-   M15 Renderer
-   M16 Alert

## Runtime

-   M17 Trade Manager
-   M18 Decision (Single Final Authority)
-   M19 State Validation
-   M20 Trade Lifecycle

## Analytics

-   M21 Performance
-   M22 Signal Quality

------------------------------------------------------------------------

# Core Principles

-   Single Responsibility
-   Single Owner
-   Engine Data Bus (EDB)
-   Public Module Contract
-   Service Layer
-   Registry
-   Dashboard Read Only
-   Renderer Owns Objects
-   Alert Owns Notifications
-   Validation Never Overrides Decision
-   Analytics Isolation
-   Append-Only Lifecycle
-   No Behaviour Change During Refactor

------------------------------------------------------------------------

# Official Runtime Flow

Foundation → Analysis → Qualification → Execution → Risk → M18 Decision
→ M17 Runtime → M19 Validation → M20 Lifecycle → M21 Performance → M22
Signal Quality → DDS

------------------------------------------------------------------------

# Phase 2 Roadmap

1.  Sprint 0 -- Documentation
2.  Sprint 1 -- Refactor M01--M04
3.  Sprint 2 -- Refactor M05--M09
4.  Sprint 3 -- Refactor M10--M13
5.  Sprint 4 -- Refactor M14--M18
6.  Sprint 5 -- Refactor M19--M22
7.  Sprint 6 -- DDS Integration
8.  Sprint 7 -- Regression
9.  Sprint 8 -- Build v0.2.0 RC

------------------------------------------------------------------------

# Freeze Rules

Allowed: - Refactor - Optimisation - Bug Fixes

Not Allowed: - Change Architecture - Change Module Ownership - Change
Runtime Flow - Add New Trading Logic Before Regression

------------------------------------------------------------------------

# Milestone

PHOENIX Architecture v1.0 is officially frozen.

Implementation starts from M01.
