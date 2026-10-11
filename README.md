# Mashuk Elahi — Marine & Offshore Electrical Engineering Portfolio

**Live site: https://mnelahi-ai.github.io/portfolio/**

Marine and offshore electrical engineer, Singapore. Sixteen years in LV/MV/HV power
systems for vessel newbuilds, offshore assets and offshore-wind applications, now
working on hybrid-electric vessel power and on the digitalisation of class-compliant
electrical design.

Class work under ABS, Bureau Veritas, Lloyd's Register and DNV.

---

## What is here

| Path | Contents |
|------|----------|
| `index.html` | The portfolio site — a React single-page app built from a separate source project and deployed as static files |
| `toolkit/` | Marine electrical calculators and reference tables: transformer short-circuit and full-load current, switchboard rating, motor full-load current and trip sizing, motor earth-fault current, cable voltage drop, fuel consumption |
| `simulations/` | Interactive explainers — hybrid vessel driveline, microgrid, energy storage, data centre power, CCHP, cable sheath current |
| `critical-facilities.html` | Secondary positioning: data centre and semiconductor critical power |
| `assets/` | CVs, the research concept note, images, and the compiled JS/CSS bundle |

## Documents

- [Marine & Offshore CV](assets/Mashuk_Elahi_Resume_Marine_Offshore_rev7.pdf) — the primary CV
- [Research CV](assets/Mashuk_Elahi_Resume_Research_rev5.pdf) — for research places and supervisors
- [Research concept note](assets/Mashuk_Elahi_Research_Concept_Note_rev3.pdf) — provenance-checked generation of class-compliant marine electrical deliverables
- [Critical Facilities CV](assets/Mashuk_Elahi_Resume_Critical_Facilities_rev4.pdf)
- [Europass CV](assets/Mashuk_Elahi_Resume_Europass_rev4.pdf)

## Current work

Delivering the hybrid-power architecture for a 42 m fast crew boat newbuild: a
three-generator 450 ekW prime-power system that took first-pass approval from four
independent certification bodies, and a 72 kWh lithium-ion BESS with BMS and DC/DC
inverters that cuts fuel draw by up to 50% at low load.

Alongside it, an engineering digitalisation toolchain in daily production use on the
same vessel. Every deliverable — a 1,300-cable schedule, a 40-drawing controlled set,
an electrical load list, an AMS alarm point list and the drawing register — is rendered
deterministically by Python generators from one data set. A compliance linter gates
every issue, every engineering value carries a machine-checkable record of where it came
from, and a release is accepted only when two independent builds come out byte-identical.

## Deployment

Static files served by GitHub Pages from the repository root. The site is compiled from a
separate React + TypeScript source project; `README_HOW_TO_PUBLISH.md` records the
publishing steps, and `PORTFOLIO_SUMMARY.md` the site's contents.

## Contact

Singapore · [LinkedIn](https://www.linkedin.com/in/mashukelahi/) · m_nelahi@yahoo.com
