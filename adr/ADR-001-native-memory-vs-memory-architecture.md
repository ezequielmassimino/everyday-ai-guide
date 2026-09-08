# ADR-001: Native Sana Memory feature vs. Memory Architecture — scope and relationship

**Status:** accepted

**Date:** 2026-09-08

**Deciders:** Pilo Massimino (Architect, v1)

## Context

Sana has shipped a native "Memory" feature: an explicit-trigger-only, unstructured personal fact/preference store with no automated capture. This project independently uses "memory" to describe a much larger, automated, structured, multi-file system across nine sub-projects. The naming collision creates real risk of readers (and the Sub-project 7 Q&A Live Agent) conflating the two, or worse, assuming the native feature already satisfies part of this project's automation requirements.

## Decision

The native Sana Memory feature is treated as a distinct, narrower capability — not an implementation of, substitute for, or partial delivery of Sub-project 2 (Scheduled Sana Agent) or the five-file schema. It is recognised only as a native equivalent of the project's own **quick capture** mechanism (Section 8), and as a lightweight, informal stand-in for isolated entries that would otherwise live in `working-preferences.md` (Layer B — Individual).

## Rationale

- Native Memory is explicit-trigger-only ("remember that..."), the opposite of this project's core design principle of automated capture by default.
- Native Memory stores unstructured facts with none of the mandatory `source` / `captured` / `confidence` provenance fields this project requires on every entry.
- Native Memory has no review queue, confidence threshold, or entry-level undo, since every entry is user-initiated.
- Native Memory is individual-scoped only, with no Layer A (team) or Layer 0 (organisation) equivalent.

## Alternatives considered

- Treat native Memory as fulfilling Sub-project 2's role — rejected; it performs no extraction from meetings, email, calendar, Workday, or any connected source.
- Rename this project's memory files/sub-projects to avoid the naming collision — deferred; a documentation/glossary clarification is judged sufficient for now.

## Consequences

- Sub-project 8's interview may optionally also invoke native Memory as a convenience, but `working-preferences.md` remains the system of record.
- Sub-project 7 (Q&A Live Agent) should be updated to explain this distinction when asked.
- Revisit this ADR if Sana's native memory later adds automated capture, schema/provenance, or team/org scoping (relevant to the Version 4 aspiration in Section 18).
- No re-architecture of this project is required.

## Related

Section 2 (What this project is), Section 8 (Quick capture), Section 18 (Platform independence — Version 4 vision), Sub-project 7, Sub-project 8, Sub-project 9
