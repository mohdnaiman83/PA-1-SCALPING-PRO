# PHOENIX Core Engineering Standards v1.0

Project: PA-1 SCALPING PRO (PHOENIX)

## Status

-   Core Standard v1.0: FROZEN
-   Rules #001--#025: Locked
-   Extension Standards: #026 Performance, #027 Reliability
-   Next Target: Build 0.2.0 (Architecture → Code)

## Core Rules Summary

1.  Refactor Structure, Never Behaviour
2.  One Direction Data Flow
3.  Module Isolation
4.  Standard ModuleResult
5.  DDS Observes Only
6.  Regression Before Progress
7.  Architecture Freeze
8.  Contracts Over Implementation
9.  Services Over Duplication
10. One Candle = One Lifecycle
11. No Build Without Certification
12. DDS Viewer is Consumer
13. Standard Diagnostic Codes
14. Module Health ≠ Trading Quality
15. Standard Engine Events
16. One Engine State at a Time
17. Kernel Orchestrates
18. Interface Boundaries
19. Change Classification
20. Engineering Constitution
21. PHOENIX Development Lifecycle
22. Design Authority
23. Build Release Gates
24. Engineering Traceability
25. Documentation Governance

## Engineering Constitution

-   Engine Integrity First
-   Deterministic Execution
-   Observability by Design
-   Separation of Responsibility
-   Architecture Before Features
-   Evidence Before Assumption
-   Build for Longevity

Engineering Oath: "We optimize for correctness, maintainability and
longevity."

## Architecture Stack

Configuration → Kernel → Services → Execution Pipeline → Modules
(M01--M22) → Trade Manager → Dashboard → DDS Viewer

DDS Philosophy: Engine Thinks. DDS Observes. Trader Executes.

## PDLC

Idea → Architecture Review → Design → Implementation → DDS Verification
→ Regression → Certification → Release

## Build Lifecycle

Planned → Development → Integration → Validation → Certified → Released
→ Archived

## Extension Standards

Rule #026: Performance optimization shall preserve deterministic
behavior and architectural integrity.

Rule #027: Every failure shall be deterministic, diagnosable, and
recoverable without compromising engine integrity.

## Immediate Roadmap

Build 0.2.0 - Refactor Modules - DDS Hooks - Regression - Testing -
Release

Architecture work is frozen unless implementation reveals a genuine
architectural issue.
