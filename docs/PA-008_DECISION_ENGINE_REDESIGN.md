# PA-008 : Decision Engine Redesign
Project : PA-1 SCALPING PRO (PHOENIX)
Status  : LOCKED
Date    : 23 Jul 2026

---

# Background

Architecture audit found that Module 18 currently functions primarily as a gate controller and score calculator.

Although Modules M05–M10 generate rich analytical data, most of that information is not consumed by the Decision Engine.

Current flow:

M05
    ↓
m05_ready (bool)
    ↓
M18
    ↓
+20 Score
    ↓
BUY / SELL

Result:
Decision quality is limited because most evidence is discarded before reaching M18.

---

# Findings

## M05

Current outputs include:

- Swing
- BOS
- CHOCH
- Trend
- Structure State
- Confidence
- Strength
- Reason Code

However only:

m05_ready

is consumed by M18.

---

## M18

Current responsibilities:

- Mandatory Gate
- Weight Calculator
- Decision Filter
- Final BUY / SELL
- Dashboard Sync

Current weakness:

Decision logic uses module readiness instead of analytical evidence.

Example:

if m05_ready
    +20

instead of analysing:

- Trend
- Confidence
- BOS
- CHOCH
- Structure Strength

---

# Locked Design

M05

Remain as Evidence Generator.

No major engine rewrite during this phase.

Upgrade Shadow API only.

Export additional evidence:

- Trend
- Structure State
- BOS
- CHOCH
- Confidence
- Strength
- Reason

---

M18

Upgrade from:

Decision Gate

to

Decision Brain

---

New Internal Flow

Evidence
↓

Direction Engine

↓

Evidence Weight Engine

↓

Conflict Engine

↓

Confidence Engine

↓

Decision Filter

↓

Final Decision

↓

BUY / SELL / WAIT

---

Direction Engine

Compare:

- HTF
- Structure Trend
- Market Bias

Detect alignment.

---

Evidence Weight Engine

Instead of:

Ready = +20

Evaluate:

Trend

Confidence

BOS

CHOCH

Liquidity

Premium / Discount

Order Block

Mitigation

Market Bias

Each evidence contributes independently.

---

Conflict Engine

Detect conflicts such as:

Bull Trend
Bear Bias

Bull BOS
Bear OB

Fresh CHOCH
Bull Continuation

Conflict reduces score or forces WAIT.

---

Reasoning Engine

Decision must include explanation.

Example:

BUY

Reason

✔ Bull Trend
✔ HTF Align
✔ Fresh BOS
✔ SSL Sweep
✔ Discount
✔ Fresh OB

---

Dashboard

Future Dashboard should display:

Trend

Bias

Conflict

Confidence

Decision Score

Decision Reason

instead of only PASS / FAIL.

---

Implementation Roadmap

Sprint A

✓ Upgrade M05 Shadow API
(No Engine Rewrite)

Sprint B

✓ Redesign M18 Decision Logic

Sprint C

✓ Functional Audit of M05
(Only if required)

---

Expected Benefits

- Better decision quality
- Modular architecture
- Easier debugging
- Explainable BUY / SELL
- Future-ready for DDS integration

---

STATUS

LOCKED

PA-008
Decision Engine Redesign
