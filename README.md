# eBike BMS — Systems Engineering Case Study

 <img src="ProflePictureComp.jpg" alt="Sherif ElFiky" width="150">

I'm Sherif ElFiky, a System Engineer / Technical Project Manager with 15+ years across automotive and Public sector programs (Bosch, Volkswagen, Stellantis, Porsche), IREB CPRE-certified. I'm moving more toward electrification roles, and wanted a concrete way to show how I'd approach one. So I picked a self contained, safety relevant component (an eBike Battery Management System) and worked it end to end: context, architecture, interfaces, and a protection use case with full traceability to verification. This isn't a claim of BMS product experience it's a record of the systems engineering process I bring to a new domain.

## Structure

This case study follows a standard automotive V-model flow, one document per stage:

1. **System Context**  purpose, stakeholders, system boundary, and external interfaces at a glance.
2. **Architecture**  functional decomposition of the BMS into its core blocks, with design rationale for each.
3. **Interfaces (ICD)**  a formal Interface Control Document covering every external and internal signal: protocol, range, and failure behavior.
4. **Overload Protection Use Case**  the centerpiece: a concrete trigger scenario, requirements, an FMEA-style risk analysis (RPN), design response, sequence diagram, and verification test cases.

## How this maps to automotive systems engineering practice

| V-model / ASPICE phase | This case study's artifact |
|---|---|
| System Requirements (SYS.1/SYS.2) | Requirements embedded in each doc section |
| System Architecture (SYS.3) | [02-architecture.md`](02-architecture.md) |
| Interface Requirements | [03-interfaces.md`](03-interfaces.md) (ICD) |
| Qualification Test (SYS.5) | Verification section in the use case doc |

## Contents

- [System Context](01-system-context.md)
- [Architecture](02-architecture.md)
- [Interfaces (ICD)](03-interfaces.md)
- [Overload Protection Use Case](04-overload-protection-use-case.md)

## Disclaimer

This is a generic/idealized eBike platform, not a real reference product.

---

📩 Sherif ElFiky - sherif_badr@hotmail.com - +4915256024083
