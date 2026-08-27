# ARCHETRON External Learning Loop

**Status:** LOCKED
**Date:** 2026-08-26

## Purpose

This document records the locked architecture established for externally observing, preserving, and evaluating AI chat interactions when the acting chat model itself cannot reliably perform a post-response learning audit.

The design is an external approximation of functions intended to exist inside ARCHEngine.

## Core Flow

```text
AI CHAT RUNTIME
        ↓
PEEP
        ↓
RATTER
        ↓
COMPANION / EVALUATOR
        ↓
RULE CANDIDATE / LAW CANDIDATE / NO ACTION
```

The core separation is:

```text
PEEP SEES
RATTER CAPTURES
COMPANION INTERPRETS
```

## PEEP — Sensing Layer

PEEP observes browser-side events after content reaches and is processed by the browser.

PEEP does not need access to a provider's internal API or private transport mechanism. Once an AI response reaches the browser and is unpacked/rendered by the web application, that externally observable browser activity is sufficient for PEEP to sense.

PEEP's responsibility is observation and normalization, not interpretation.

For chat interactions, the relevant future observation path is:

```text
user message becomes observable
        ↓
assistant response arrives / renders
        ↓
completed assistant turn becomes observable
        ↓
PEEP emits normalized interaction events
```

PEEP must not decide whether the model learned anything.

## DEVSnitcher — Component Mine, Not Replacement

DEVSnitcher remains its own standalone product.

It is not being converted into the chat observer and it is not being replaced.

However, DEVSnitcher already contains browser-side capture machinery that may be mined or reused when building PEEP's browser observation capability, including patterns or components for:

- browser extension orchestration;
- background service workers;
- content-script to page-context bridging;
- DOM/page-context observation;
- lazy script injection;
- request/response messaging;
- double-injection protection;
- evidence collection;
- redaction; and
- deterministic structured output.

The value of DEVSnitcher in this architecture is reuse of proven browser capture plumbing.

## RATTER — Capture and Preservation Layer

The product name is **RATTER**.

RATTER receives normalized observations from PEEP and preserves the operational record.

RATTER owns durable capture concerns such as:

- runtime identity;
- session identity;
- turn identity;
- event identity;
- ordering and sequence;
- integrity;
- continuity and missing-event detection; and
- durable evidence of what was observed.

RATTER does not decide what the interaction means.

Its role is to keep the receipt.

## Companion / Evaluator — Interpretation Layer

The companion is a separate process from the acting chat agent.

It may use a completely different model and a separate API call.

It evaluates completed interaction records after the acting model has already responded.

Its central question is:

> Did this interaction establish a durable operating lesson that should affect future behavior?

Possible outcomes:

```text
NO DURABLE LESSON
→ no action

RULE CANDIDATE
→ evaluate under the current LAWS/RULES authority
→ persist to RULES.md only when authorized by that authority

LAW CANDIDATE
→ surface to Darren
→ requires Darren's explicit authorization before LAWS.md changes
```

The companion is not part of the user-facing chat response loop and does not need the acting model to retain unused post-response execution capacity.

## Why the Evaluator Is Separate

The acting chat model cannot be relied upon to execute a hidden post-send reflection step after its final response has already been emitted.

Moving evaluation outside the acting model removes that timing dependency.

The evaluator sees the completed interaction as an external object of observation rather than attempting to audit itself while generating the response.

## Interaction Record

The preferred evaluation unit is the completed interaction, not an isolated assistant message.

Where available, the record should preserve both sides:

```text
USER MESSAGE
+
ASSISTANT RESPONSE
+
RUNTIME / SESSION / TURN IDENTITY
+
OBSERVATION / INTEGRITY METADATA
```

This allows the evaluator to distinguish a model-generated idea from an actual correction, instruction, demonstrated failure, or durable lesson established through interaction.

## Architectural Boundaries

- PEEP observes; it does not reason about learning.
- RATTER preserves; it does not decide meaning.
- The companion interprets; it does not become the acting chat agent.
- DEVSnitcher remains a separate product and serves only as a source of reusable browser-capture technology where appropriate.
- The acting chat model does not need to perform its own post-response learning audit.
- RULES remain subordinate to LAWS.
- LAW changes remain under Darren's explicit authority.

## ARCHEngine Relationship

This external loop is a practical approximation of behavior intended to exist inside ARCHEngine.

It externalizes several functions around an otherwise stateless or session-limited chat model:

```text
observation
→ persistence
→ completed-event inspection
→ lesson admission
→ governance
→ controlled adaptation
```

The external system is not the final ARCHEngine implementation. It is a way to reproduce part of that behavior using currently available components and model APIs.
