---
artifact: starter-prompts-jury-synthesis
jurors:
  - model: claude-opus-4.6
    role: Domain Sceptic
    r1_verdict: NEEDS_REVISION
    r2_verdict: NEEDS_REVISION
  - model: claude-sonnet-4.5
    role: Technical Expert
    r1_verdict: NEEDS_REVISION
    r2_verdict: NEEDS_REVISION
  - model: gpt-5.4
    role: Strategic/Product Lens
    r1_verdict: NEEDS_REVISION
    r2_verdict: NEEDS_REVISION
  - model: gpt-5-mini
    role: Defense Counsel
    r1_verdict: NEEDS_REVISION
    r2_verdict: NEEDS_REVISION
  - model: gpt-5.4-mini
    role: Devil's Advocate
    r1_verdict: NEEDS_REVISION
    r2_verdict: NEEDS_REVISION
synthesizer: claude-opus-4.5
phase: adoption-guide
slice: starter-prompts
project: build-adoption-guide-2026-001
verdict: APPROVED_WITH_CORRECTIONS
round: R2
---

# Jury Synthesis: Starter Prompts (P1–P7)

## Executive Summary

The jury reviewed seven starter prompts for the Hangar AI Constitution "Getting Started in 15 Minutes" guide across two deliberation rounds. All five jurors returned NEEDS_REVISION verdicts in R1 (round-robin). R2 (Delphi) achieved convergence on required corrections for P1–P5, with P6 and P7 approved subject to non-blocking advisories.

**Overall Verdict: APPROVED_WITH_CORRECTIONS**

The corrections are clear, agreed upon by all jurors, and do not require fundamental redesign of the starter prompts. Implementation can proceed once the specified changes are applied.

---

## R1 Summary (all 5 NEEDS_REVISION — 7 corrections identified)

| ID | Prompt | Issue | Severity |
|----|--------|-------|----------|
| C-001 | P1 | No guard if constitution not found or wrong directory | LOW |
| C-002 | P2 | Soft preference — agent could proceed after preview | HIGH |
| C-003 | P3 | "resolve avatars" is optional, not mandatory; heavy jargon | HIGH |
| C-004 | P4 | "Phase 1 Capture" does not exist — actual phase is "Phase 1 Domain" | CRITICAL |
| C-005 | P5 | Entry point implies unknown; it's always Phase 0 Decision Track | CRITICAL |
| C-006 | P6 | Steps technically accurate; UX outcome language advisory only | ADVISORY |
| C-007 | P7 | Intentionally broad; 4/5 jurors approve breadth | ADVISORY |

## R2 Summary (all 5 NEEDS_REVISION converged — 5 corrections confirmed)

All 5 corrections (C-001 through C-005) confirmed by all 5 jurors. Two non-blocking advisories raised:

- **NF-R2-001 (J3):** P6 could add explicit APPROVED/OBJECTED outcome language — non-blocking
- **NF-R2-002 (J2):** P7 could specify TDD enforcement and ENG law validation — overridden 3-2 majority

## Contradiction Resolutions

**P5 — Decision Track vs Phase 1 Assess (RESOLVED):**
J1 (Domain Sceptic) cited legacy-rescue workflow documentation confirming Phase 0 Decision Track is explicitly labeled the "Required Entry Point". J2 (Technical Expert) had proposed "Phase 1 Assess" in R1 but conceded in R2 upon reviewing J1's citation. All 5 jurors converged on Phase 0 Decision Track as the correct entry point. "Phase 1 Assess" is the first *execution* phase after Decision Track produces its REFACTOR/REWRITE/HYBRID ruling — it cannot be reached without Phase 0.

## Non-Blocking Advisories

- **NF-R2-001 (J3, gpt-5.4):** P6 — consider adding explicit APPROVED/OBJECTED outcome language. Non-blocking; current steps are technically accurate per J1/J2 domain verification.
- **NF-R2-002 (J2, claude-sonnet-4.5):** P7 — consider specifying TDD enforcement and ENG law validation. Non-blocking; 3-2 majority held that broadness is intentional for a daily session primer.

## Judicial Synthesis Verdict

Synthesizer (claude-opus-4.5) verified all 5 corrections confirmed by all 5 jurors in R2. Two advisories confirmed non-blocking. Defense Counsel (J4) retracted prior APPROVED verdicts on P4 and P5 in R2 upon reviewing J1's domain evidence — demonstrating proper Delphi convergence behavior.

The prompts are fundamentally sound in structure and intent. The corrections address terminology accuracy (P4, P5), safety guards (P1, P2), and jargon/optionality (P3) without requiring redesign.

**VERDICT: APPROVED_WITH_CORRECTIONS**

## Final Corrections To Apply

| ID | Prompt | Correction | Severity | Final Wording |
|----|--------|-----------|----------|---------------|
| C-001 | P1 | Add stop-if-not-found guard | LOW | See P1 corrected below |
| C-002 | P2 | Explicit hard stop + wait for approval | HIGH | See P2 corrected below |
| C-003 | P3 | Plain language; avatar optional | HIGH | See P3 corrected below |
| C-004 | P4 | "Phase 1 Capture" → "Phase 1 Domain" | CRITICAL | See P4 corrected below |
| C-005 | P5 | Explicit Phase 0 Decision Track entry | CRITICAL | See P5 corrected below |

## Corrected Prompt Wording

**P1 — Main Setup Prompt (corrected):**
```
Run the setup installer from the Hangar AI Constitution to set up constitutional governance in my workspace. If you cannot locate the constitution or are not in the workspace root, stop and tell me before making any changes.
```

**P2 — Preview Addendum (corrected):**
```
Before writing any files, show me exactly what changes you would make, then stop and wait for my explicit approval.
```

**P3 — Adopt the Constitution (corrected):**
```
Adopt the Hangar AI Constitution in this repo. Check the current adoption state, create or update AGENTS.md, create hangar-ai-specs/ if it doesn't exist, and confirm the setup is valid. Let me know if avatar configuration is needed — we can handle that as a separate step.
```

**P4 — Greenfield Feature (corrected):**
```
I'm building [feature name]. Walk me through the Hangar greenfield workflow starting with Phase 1 Domain, tied to story [story ID].
```

**P5 — Legacy Module (corrected):**
```
I need to improve [module or feature] in this codebase. Start the Hangar legacy rescue workflow at Phase 0 Decision Track and help me assess whether to refactor, rewrite, or split before moving to Phase 1.
```

**P6 — Phase Gate (no change):**
```
We've completed Phase [N] for [feature]. Run the phase gate — citation audit, 5-juror jury, synthesis, and gate check.
```

**P7 — Daily Work (no change):**
```
I'm working on story [story ID]: [title] today. Use the Hangar AI Constitution to guide my implementation and keep me aligned with our engineering standards.
```

---

*Synthesized: 2026-06-16*
*Protocol: PRD-2.6 Multi-Cognition Jury Review*
*Rounds: R1 (Round-Robin) → R2 (Delphi)*
