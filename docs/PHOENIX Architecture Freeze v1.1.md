# PHOENIX Architecture Freeze v1.1

## Project

-   **Project:** PA-1 SCALPING PRO
-   **Codename:** PHOENIX
-   **Status:** Architecture LOCKED
-   **Policy:** Zero Behavior Change

------------------------------------------------------------------------

## Architecture Layers

### Infrastructure

-   M01 Core Framework ✅ LOCK
-   M02 Configuration ✅ LOCK

### Producer Layer

-   M03 Market Engine ✅ LOCK
-   M04 HTF Engine ✅ LOCK
-   M05 Structure ✅ LOCK
-   M06 Liquidity ✅ LOCK
-   M07 Premium/Discount ✅ LOCK
-   M08 Order Block ✅ LOCK
-   M09 Mitigation ✅ LOCK
-   M10 Evidence ✅ LOCK
-   M11 Qualification ✅ LOCK
-   M12 Execution ✅ LOCK
-   M13 Risk ✅ LOCK

### Runtime Layer

-   M17 Trade Lifecycle ✅ LOCK
-   M18 Decision Engine ✅ LOCK
-   M19 Validator ✅ LOCK
-   M20 Trade Manager ✅ LOCK
-   M21 Statistics ✅ LOCK
-   M22 Dashboard Feed ✅ LOCK

------------------------------------------------------------------------

## Producer Standard

Every producer module shall contain: 1. Public API 2. Shadow Mapping 3.
DDS Hook

No business logic is allowed in these sections.

------------------------------------------------------------------------

## Infrastructure Rules

### M01

-   Runtime owner
-   Global state
-   Constants
-   Renderer base
-   No Public API
-   No DDS

### M02

-   Configuration owner
-   cfg\_\* variables
-   No Public API
-   DDS optional (future)

------------------------------------------------------------------------

## Runtime Exceptions

These remain runtime owners:

-   g_tradeState
-   g_signal
-   g_engineStatus
-   g_tradeActive
-   g_entry
-   g_sl
-   g_tp1
-   g_tp2
-   lc\_\*

------------------------------------------------------------------------

## Consumer Rules

Consumers must use Public API (`m*_`) only.

Legacy producer variables (`e_*`) are not allowed for new consumer
development.

Runtime owner exceptions remain valid.

------------------------------------------------------------------------

## PA-013 Roadmap

1.  Consumer Audit
2.  Dashboard Migration
3.  Renderer Migration
4.  Labels / Tables Migration
5.  Alerts Migration
6.  Legacy Cleanup
7.  Regression Test
8.  Build Freeze

------------------------------------------------------------------------

## Locked Decisions

-   Zero Behavior Change
-   Compile → Regression → Lock
-   Producer owns data
-   Consumer consumes Public API only
-   Runtime owner exceptions preserved

------------------------------------------------------------------------

**Document:** PHOENIX Architecture Freeze v1.1
