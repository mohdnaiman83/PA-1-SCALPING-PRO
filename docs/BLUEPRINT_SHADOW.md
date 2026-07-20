# PA-1 SCALPING PRO (PHOENIX)

# PA-007.1.1 --- Shadow Migration Blueprint

**Status:** STARTED\
**Build Target:** v0.7.0-alpha\
**Architecture:** Hybrid Mode (Locked)

------------------------------------------------------------------------

# Purpose

Introduce the new Module 05 architecture without breaking the existing
production engine.

The Legacy Structure Engine remains the production source while the new
Structure API is built in parallel.

------------------------------------------------------------------------

# Migration Strategy

    Legacy M05
          │
          ├──────────────► Legacy API
          │
          └──────────────► Shadow API
                              │
                       Validation
                              │
                     Regression Test
                              │
                     Production Switch

------------------------------------------------------------------------

# Engineering Principle

Do **NOT** replace Module 05 in one shot.

Use **Shadow Migration**.

Benefits:

-   Zero downtime
-   Easy regression tracking
-   Easy rollback
-   Incremental verification

------------------------------------------------------------------------

# Sprint A (Current)

Objective:

Create the new Structure API only.

No trading logic changes.

No scoring changes.

No dashboard changes.

No signal changes.

------------------------------------------------------------------------

## Public API

``` pine
e_structureBullBias
e_structureBearBias
e_structureNeutral

e_structureConfidence

e_lastSwingHigh
e_lastSwingLow

e_structureRangeReady

e_bosBullEvidence
e_bosBearEvidence

e_chochBullEvidence
e_chochBearEvidence
```

These variables mirror the legacy outputs during the migration stage.

------------------------------------------------------------------------

# Legacy Policy

The following variable remains active:

``` pine
e_structureReady
```

Status:

-   Deprecated
-   Production Active
-   Planned Removal: PA-008

------------------------------------------------------------------------

# Migration Phases

## Phase A

Create Shadow API.

Production uses Legacy.

------------------------------------------------------------------------

## Phase B

Enable Debug Validation.

Dashboard (Developer Mode):

    Legacy Structure : PASS

    Shadow Structure : PASS

    Sync : OK

------------------------------------------------------------------------

## Phase C

Evidence Engine starts consuming:

    e_structureConfidence

Legacy logic remains the primary reference.

------------------------------------------------------------------------

## Phase D

Switch production from Legacy API to Shadow API.

Remove deprecated variables after successful regression.

------------------------------------------------------------------------

# Safety Gates

Every phase must satisfy:

-   Compile PASS
-   Runtime PASS
-   Dashboard PASS
-   Signal Count ≈ Legacy
-   Trade Manager PASS
-   Regression PASS

If any gate fails:

-   Stop
-   Roll back
-   Fix
-   Re-test

------------------------------------------------------------------------

# Development Rules

1.  One module at a time.
2.  One objective per sprint.
3.  No architecture shortcuts.
4.  No hidden dependencies.
5.  API-first design.
6.  Backward compatibility before removal.

------------------------------------------------------------------------

# Current Project Status

-   PA-006 Mandatory Gate Audit: LOCKED
-   PA-007 Hybrid Architecture: LOCKED
-   PA-007.1 API Design: LOCKED
-   PA-007.1.1 Shadow Migration: STARTED

Next Coding Session:

-   Implement Shadow API in Module 05.
-   Keep Legacy logic untouched.
-   Verify API parity.
-   Prepare for Structure Confidence migration.

------------------------------------------------------------------------

## PHOENIX Engineering Motto

> Build with evidence.\
> Refactor with confidence.\
> Deploy only after regression passes.

End of Document.
