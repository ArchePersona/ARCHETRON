# ARCHETRON

**What does intelligence require before it can be trusted with the future?**

That is the question behind ARCHETRON.

ARCHETRON is the technology ecosystem built by **VOLSHi**.

AI is getting more capable very quickly. But being capable is not the same thing as being trustworthy.

If an AI system is going to do important work, we need more than a good answer at the end. We need to know what happened while the work was being done. We need to know what information the system used, what changed, what failed, where human approval mattered, and whether the result can be checked later.

ARCHETRON exists to provide that missing layer.

## The thesis

Most of today's AI stack is focused on making models smarter.

We think the next problem is different:

**How do you safely operate intelligence once it can act on its own?**

That requires systems around the model.

Systems that can:

- see what is happening
- preserve what happened
- understand what the data supports
- decide where attention should go
- control important boundaries
- keep people in the loop when they matter
- build software in a repeatable way
- show enough evidence that the work can be checked later

Those systems form ARCHETRON.

## ARCHETRON is the ecosystem

**VOLSHi is the company. ARCHETRON is the ecosystem.**

ARCHETRON is the collective system formed when its independent engines, applications, sensing layers, governance components, and operator controls work together.

Each project solves a different part of the problem. Some are useful on their own. Together, they form ARCHETRON.

```text
                              ARCHETRON

        SEE              UNDERSTAND             DECIDE
        PEEP                ERIE                  ARCHE
          │                   │                     │
          └───────────────────┼─────────────────────┘
                              │
                         GOVERN / WATCH
                    GATEHOUSE • ARCHERAT
                              │
                         HUMAN CONTROL
                           CTRL TOWER
                              │
          ┌───────────────────┴───────────────────┐
          │                                       │
     BUILD SOFTWARE                         INVESTIGATE WORK
       ARCHEMADA                                SHERLOCK
          │
     ARCHESTRATOR

                     PERSONA CREATION
                          NIRMATA
                              │
                            ARCHE
```

The point is not that everything has to run through one giant program.

The point is that each system has a clear job and can work with the others without becoming the others.

## The pieces

### ARCHE

ARCHE is an attention engine.

Intelligence has limited time, context, compute, and attention. ARCHE decides where the next unit of cognition should be spent based on pressure, consequence, and user cost.

It does not decide what is true. It decides what deserves attention next.

### NIRMATA

NIRMATA is the persona creation engine for ARCHE.

It is responsible for creating the personas that ARCHE can run.

### ERIE

**ERIE — Epistemic Retrieval & Intelligence Engine** — transforms disconnected data into structured evidence with context, relationships, and provenance.

Its job is to help other systems understand what the available data actually supports.

### PEEP

PEEP is the sensing layer.

It watches real execution — terminals, IDEs, runtimes, browsers, CI systems, and other sources — and turns what it observes into a common stream of events.

PEEP does not reason, build, or govern.

**It sees.**

### ARCHERAT

ARCHERAT is the observation and telemetry engine.

It gives operators a live view of what systems are doing and preserves the operational record needed to inspect behavior later.

The current code still lives in the repository historically named `ratter`; the product name is ARCHERAT.

### GATEHOUSE

GATEHOUSE is the authority and governance engine.

When something crosses an important boundary, GATEHOUSE decides whether it should be approved, denied, paused, resumed, escalated, revoked, or sent to a human for authorization.

### CTRL TOWER

CTRL TOWER is the operator-facing control application for the ecosystem.

It is where a person can see live system state, execution activity, telemetry, governance decisions, costs, and anything that needs human attention.

### ARCHESTRATOR

ARCHESTRATOR is the software engineering engine.

Most AI coding tools focus on producing code. ARCHESTRATOR manages the work around the code: planning, execution, verification, progress, saved state, and a record of what happened.

It is the engine underneath ARCHEMADA.

### ARCHEMADA

ARCHEMADA is the user-facing software engineering application.

The idea is simple: describe what you want built, work through the important planning decisions, approve the plan, and let the system carry the work through a controlled engineering process.

### SHERLOCK

SHERLOCK is an evidence reconstruction application.

It takes messy project history — conversations, files, documents, code, attachments, and timelines — and rebuilds what happened so people can answer questions from evidence instead of memory.

### DEVSnitcher

DEVSnitcher is the local-first browser evidence-capture utility.

Press **SNITCH**, and it collects the evidence already surrounding a browser failure — console errors, failed requests, runtime exceptions, environment details, and useful page context — redacts obvious secrets, and packages the result into a portable report for an AI assistant, issue, chat, or human debugger.

It does not diagnose the bug, call an AI, require an account, or depend on a backend. Its job is to make the evidence at the browser edge easy to capture and move.

Within the larger ARCHETRON evidence model, DEVSnitcher is deliberately narrow: capture first. Deeper reconstruction and evidence reasoning belong to systems such as SHERLOCK and ERIE.

## Why separate systems?

Because giant AI systems become impossible to trust when every responsibility is mixed together.

The thing that watches execution should not quietly become the thing that grants permission.

The thing that decides what the data supports should not also decide where cognitive attention goes.

The application a person uses should not have to own the engine underneath it.

ARCHETRON is built around clear boundaries so each part can be inspected, replaced, tested, and improved without turning the entire ecosystem into one giant black box.

## What VOLSHi is trying to prove

The long-term bet behind ARCHETRON is that trustworthy autonomous intelligence will need more than models.

It will need infrastructure for observation, evidence, governance, attention, execution, history, and human control.

VOLSHi is building those pieces now.

Not because AI needs more dashboards.

Because if intelligence is going to take on more responsibility, we need better answers to a much more important question:

**Why should we trust what it just did?**

## The Nerd Section

The public idea is simple: make autonomous intelligence easier to observe, govern, verify, and trust.

The implementation is intentionally split across independent engines, applications, event boundaries, persisted state, provenance, and operator controls. The individual repositories contain the technical material that is appropriate to publish for each system.

## Ecosystem repositories

- **ARCHE** — attention engine
- **ARCHEMADA** — software engineering application
- **ARCHESTRATOR** — software engineering engine
- **ERIE** — Epistemic Retrieval & Intelligence Engine
- **SHERLOCK** — evidence reconstruction
- **DEVSnitcher** — local-first browser evidence capture and portable debugging reports
- **PEEP** — execution observation
- **ARCHERAT** — telemetry and operational observation (currently in the `ratter` repository)
- **GATEHOUSE** — authority and governance
- **CTRL TOWER** — operator control application
- **NIRMATA** — persona creation engine for ARCHE

**Together, they are ARCHETRON. ARCHETRON is a VOLSHi technology ecosystem.**
