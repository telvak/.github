# Telvak — Community Health Files

This repository contains the default community health files for the [Telvak](https://github.com/telvak) organization. GitHub applies these files across all Telvak repositories that do not define their own.

---

## What Lives Here

| File | Purpose |
|---|---|
| `profile/README.md` | Public org homepage at github.com/telvak |
| `CONTRIBUTING.md` | How to contribute to any Telvak repository |
| `CODE_OF_CONDUCT.md` | Community standards and expectations |
| `SECURITY.md` | How to report security vulnerabilities |

---

## Repository Guide

New to the Telvak codebase? Start here.

**Want to understand the platform?**
→ Read the [platform repo](https://github.com/telvak/platform) — this is the core of everything.

**Want to build a carrier connector?**
→ Read [CONTRIBUTING.md](CONTRIBUTING.md) then use [connector-twilio](https://github.com/telvak/connector-twilio) as your reference implementation.

**Found a security issue?**
→ Read [SECURITY.md](SECURITY.md) before disclosing anything publicly. We take this seriously.

**General contribution questions?**
→ Open a discussion in the [platform repo](https://github.com/telvak/platform/discussions).

---

## Core Principles Every Contributor Must Understand

Before contributing to any Telvak repository, internalize these — they are not guidelines, they are laws of the system:

1. **TenantId is sacred.** Every domain object carries a TenantId. No query runs without a tenant scope. No data crosses tenant boundaries. Ever.

2. **Consent state is a ledger, not a flag.** Never update consent state in place. Always append a new event. The history is as important as the current state.

3. **Compliance rules are data, not code.** Rule logic lives in configuration. Regulatory changes must not require platform deployments.

4. **The audit trail is immutable.** Once written, audit events are never modified, never deleted. If you are writing code that touches audit records, it must be append-only.

5. **Carriers are plugins.** The platform core has zero knowledge of specific carriers. All carrier logic lives in connectors. No Twilio SDK imports inside `Telvak.Platform`.

---

*Every message, purposefully delivered.*
[telvak.com](https://telvak.com)
