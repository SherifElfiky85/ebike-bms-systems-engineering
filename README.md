# eBike BMS — Systems Engineering Case Study

"A worked systems engineering case study on an eBike Battery Management
System: from system context through architecture, interfaces, and a
protection function use case, structured the way I'd approach a component
spec in an automotive V-model project."

## Why this case study

I'm moving toward electrification systems engineering roles, and wanted a concrete way to show how I'd approach one, beyond listing "systems engineering" on a CV. So I picked a self-contained, safety-relevant component (an eBike BMS) and worked it end-to-end: context, architecture, interfaces, and a protection use case with full traceability to verification. The goal is to show the systems engineering process that I can bring to a new domain.

## How this maps to automotive systems engineering practice

| V-model / ASPICE phase | This case study's artifact |
|---|---|
| System Requirements (SYS.1/SYS.2) | Requirements embedded in each doc section |
| System Architecture (SYS.3) | [`02-architecture.md`](02-architecture.md) |
| Interface Requirements | [`03-interfaces.md`](03-interfaces.md) (ICD) |
| Qualification Test (SYS.5) | Verification section in the use case doc |

## Contents

- [System Context](01-system-context.md)
- [Architecture](02-architecture.md)
- [Interfaces (ICD)](03-interfaces.md)
- [Overload Protection Use Case](04-overload-protection-use-case.md)