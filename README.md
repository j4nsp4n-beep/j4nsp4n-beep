# Jan Span

**AI systems integrator and operator** focused on turning models, tools, context, and permissions into reliable workflows for real work.

I build at the layer between AI capability and operational consequence: agent orchestration, deterministic verification, human approval gates, audit trails, and recoverable execution.

## How I work

```text
Model proposes → code verifies → human decides → system records
```

I prefer narrow, testable claims over broad AI promises. The central question is not whether a model can produce an answer, but whether the surrounding system can detect its failures, constrain its permissions, preserve context, and recover safely.

Each repository below isolates one such failure, reproduces it deterministically, and shows the control that catches it. All of them run on the standard library or close to it: no API key, no paid service, no model download. Clone and verify in under a minute.

## Proof

### [Verified Agent Workflow](https://github.com/j4nsp4n-beep/verified-agent-workflow)

*A citation can be real and still be wrong.*

An AI draft cites a genuine rule, but quotes wording that was not in force at the date being evaluated. The answer looks right and the source exists. Structured claims, temporally versioned sources, and deterministic validation make that failure visible instead of plausible.

[architecture and threat model](https://github.com/j4nsp4n-beep/verified-agent-workflow/blob/main/docs/architecture.md) · [CI](https://github.com/j4nsp4n-beep/verified-agent-workflow/actions)

### [Agent Permission Plane](https://github.com/j4nsp4n-beep/agent-permission-plane)

*An approval should authorise a call, not grant a capability.*

Agent permission is usually a flag, which leaves the window between the yes and the act unguarded. Here every approval is bound to a digest of the specific call, single-use, time-bounded, and scoped. Approve an email to one recipient, attempt it to another, and the approval no longer applies. Unregistered tools are denied by default, and the credential boundary sits above the class system where no approval lifts it.

[architecture](https://github.com/j4nsp4n-beep/agent-permission-plane/blob/main/docs/architecture.md) · [threat model](https://github.com/j4nsp4n-beep/agent-permission-plane/blob/main/docs/threat-model.md)

### [PII Redaction Gate](https://github.com/j4nsp4n-beep/pii-redaction-gate)

*A redaction pipeline should not certify its own output.*

Whatever a single recognition stage fails to recognise leaves the trust boundary silently and looks like success. An independent auditor reads the redacted text, asks the inverse question using its own patterns, and blocks the release. The corpus includes a document the redactor gets wrong, and the gate catches it. There is deliberately no CLEAN verdict: absence of personal data cannot be proven by the stage whose recall was the problem in the first place.

[architecture](https://github.com/j4nsp4n-beep/pii-redaction-gate/blob/main/docs/architecture.md) · [threat model](https://github.com/j4nsp4n-beep/pii-redaction-gate/blob/main/docs/threat-model.md)

### [Governed Document Intake](https://github.com/j4nsp4n-beep/governed-document-intake-n8n)

*The write is the moment everything can go wrong.*

Deterministic financial-document controls with approvals bound to input hash, duplicate prevention, and evidence receipts. The ledger records and flushes a `RESERVED` intent before the write, then commits or fails; a leftover `RESERVED` fails closed for reconciliation rather than guessing. Includes an n8n export using core nodes only, with an independent graph validator.

[architecture](https://github.com/j4nsp4n-beep/governed-document-intake-n8n/blob/main/docs/architecture.md) · [threat model](https://github.com/j4nsp4n-beep/governed-document-intake-n8n/blob/main/docs/threat-model.md)

## What I build

- **Agent workflows:** context assembly, tools, specialist workers, state, and recovery
- **Verification systems:** evaluations, deterministic validators, evidence trails, and failure ledgers
- **Human control:** explicit approval boundaries for consequential actions
- **Operational integrations:** AI connected to existing business systems rather than isolated chat demos

## A note on the limitations sections

Each repository documents what it does not do, in detail: the races, the recall gaps, the difference between demonstrating a mechanic and producing evidence you could rely on. Those sections are the point, not a disclaimer. A control whose boundaries are not stated is a control nobody can trust, and in this domain the failure modes are the interesting part.

## Current direction

Public, sanitized reference implementations derived from patterns used in private AI operating and verification systems. Next proof areas are realtime voice-agent reliability and agent operations control planes under concurrency.

Open to remote roles and collaborations involving AI systems integration, agentic workflows, technical operations, solution architecture, and governed automation.
