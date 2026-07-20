# PA-1 SCALPING PRO (PHOENIX)

# PA-007 --- Engine Logic Refactor Report

**Status:** STARTED

## Objective

Refactor the engine architecture to follow the native PA-1 trading SOP.

## Locked Modules

-   M01 Core
-   M02 Session
-   M03 Market
-   M04 HTF
-   M10 Evidence
-   M11 Qualification
-   M12 Execution
-   M13 Risk
-   M14 Dashboard
-   M15 Renderer
-   M16 Alerts
-   M17 Trade Manager
-   M18 Decision
-   M19 State
-   M20 Lifecycle
-   M21 Performance
-   M22 Signal Quality

## Refactor Scope

Only: - M05 Structure - M08 Order Block - M09 Mitigation

## Root Cause

Current pipeline:

Pivot → BOS → CHOCH → Order Block → Mitigation

This causes delayed downstream activation.

## New PHOENIX Pipeline

HTF Bias → Liquidity Sweep → Premium / Discount → Order Block →
Mitigation → Immediate Rebalance → Confirmation Candle → Evidence Engine
→ Decision Engine → Trade Manager

## PA-007.1

### M05.01 Swing Context

Outputs: - e_lastSwingHigh - e_lastSwingLow - e_structureRangeReady

### M05.02 Structure Context

Outputs: - e_structureBullBias - e_structureBearBias -
e_structureNeutral

### M05.03 BOS / CHOCH Evidence

BOS and CHOCH become evidence only.

### M05.04 Public API

Expose only: - e_structureBullBias - e_structureBearBias -
e_structureNeutral - e_structureConfidence

## Engineering SOP

Audit → Design → Implement → Compile → Regression Test → Lock

## Definition of Done

-   Separate Swing / Structure / BOS
-   BOS no longer mandatory
-   Stable API
-   Compile PASS
-   Runtime PASS
-   Regression PASS

## Status

-   PA-006: LOCKED
-   PA-007: STARTED
-   PA-007.1: DESIGN PHASE
