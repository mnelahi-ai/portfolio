# PORTFOLIO COMPLETE SUMMARY

**Date:** 11 June 2026  
**Author:** Mashuk Elahi  
**Tools Used:** Perplexity Computer (Comet) + Claude Desktop  
**Portfolio:** https://mnelahi-ai.github.io/portfolio/

---

## WHAT YOU GAVE TO CLAUDE

### 1. CLAUDE.md — Your Master Instructions File

**Location on your PC:** `C:\Users\m_nel\AppData\Roaming\Claude\CLAUDE.md`  
**File attached:** `CLAUDE.md` (Rev5, 01 June 2026)

**What it does:**  
Claude reads this file automatically when it starts. It tells Claude:
- You are my second brain for marine electrical engineering
- Read ENTIRE hull folder before any action
- Extract equipment data → generate Load List, Alarm List, Cable Schedule
- Use locked formulas: 3PH PF = 0.85, 1PH PF = 0.85–0.95
- Never guess — web-search missing specs; if not found → flag [MISSING] and stop
- Source of truth: `Marine_Electrical_Equipment_List.xlsx` overrides all

**Key rules in CLAUDE.md:**
- No blank remarks — every cell must cite source doc
- Auto-tag: [MISSING], [DISCREPANCY], [CA], [TBC]
- Full folder read always — no shortcuts
- Stop on conflict — never silent changes

**Hulls managed:**
- H640, H641 (19.5m / 21m pilot/crew boats, BV Qatar)
- H656-657, H658-659 (42m FCB pairs, LR Panama)
- H675 (42m FCB, LR AMSA Australia NSCV)
- H661-662, H674 (FROZEN — reference only)

---

### 2. Hull-Specific Prompts

#### H675 Prompt (Rev6, 03 June 2026)
**File attached:** `claude_prompt_H675_ONLY_03Jun2026_Rev6.md`

**What it does:**  
Tells Claude to rebuild H675 workbook Rev 2 from:
- Annex 1 Technical Spec
- Annex 3 Maker List (05/03/2026)
- 100+ Equipment datasheets
- Z-Power MSB/AMS/NLP quote

**Key H675 facts:**
- 42m Gen 4 FCB, FRP/aluminium, LR 100A1 SSC WORKBOAT MONO G4
- AMSA NSCV 1C/2B (Australian flag)
- 3× CAT C32 1,081 kW main engines @ 2,300 RPM
- 3× CAT C7.1 150 ekW generators (conflict: MSB sized for 100 kW — CA-31 open)
- 2× DT-0075 electric bow thrusters (VFD)
- Kobelt KM Asia steering (dual 3PH pumps)
- **11-item pump set** (unique — fire duty = Bilge/GS pump, CA-30 closed)
- Voltage notation: **hyphen** `380-415V` (not `/` like other hulls)
- Standards: ASNZS 3000:2018 Amd 1–3, NSCV Part C 5B, AMSA MO 503

**Open issues (Critical Actions):**
- CA-03: No 55 Elec drawing folder (SLD/Load Calc/MSB/AMS missing)
- CA-31: Generator rating conflict (150 ekW vs MSB 100 kW design)
- CA-32: FW Pressure / Sludge / Submersible pump model conflicts

---

#### H656-657 Prompt (Rev1-B, 06 June 2026)
**File attached:** `claude_prompt_H656_H657_ONLY_06Jun2026.md`

**What it does:**  
Rebuild H656-H657 workbook Rev 1 (sister-pair, one file covers both hulls).

**Key H656-657 facts:**
- 42m Gen 4 FCB, LR SSC, Panama flag, drawing series S1257
- 3× CAT C32 main engines
- 3× Baudouin 6W105S 100 ekW generators
- **1× Hydromaster AC 3PH bow thruster** 72 kW (NOT DTG — CA-22 closed)
- Kobelt KM Asia steering model SB-808211-3B
- **10-item pump set** (includes FW/SW BT cooling pumps — unique to this hull)
- Marinelite SC90 satellite compass (Tech Spec 260526 governs)
- Voltage notation: `/` separator `380/415V`

**Structural moves (Rev1-B):**
- Compartment vent fans → moved to 5.0 (fire-safety)
- Lightning protection → moved to 9.0 (nav/comms)
- Window wiper: ONE panel DCDB1-20 drives 5 wiper heads (QTY 1 supply)
- AMS HMI Display No.2 repeater → removed

**Tech-Spec gap closure:**
- VSAT: unit excluded (buyer supply), but wiring/power provision in scope (CA-31)
- Searchlights: 3× ACR RCL-95 LED **80 W** (NOT 1 kW)
- TVs: 3 (2× 55" pax, 1× 42" mess)
- Fridges: 4 (2 galley, 2 beside galley)
- Added: Water Dispenser, InSinkErator waste grinder, inline UV steriliser

**Deep-source-read additions (Rev1-C):**
- **ER Emergency Submersible Bilge Pump** (item 6.15, 0.75 kW TBC, CA-32 open)
- Floodlights: 4× **400 W** (corrected from 300 W)

**Open issues:**
- CA-04: Steering Gear drawings -26-028/-029 missing
- CA-05: 55 Elec submission gap (Load Calc/MSB/Panel/Cable/AMS/Light/CCTV)
- CA-32: ER Emergency Bilge Pump power TBC
- CA-33: Sat Compass model conflict (Tech Spec Marinelite SC90 vs Comnav G2)

---

### 3. Project Deep Analysis

#### H643-H644 Analysis (10 June 2026)
**File attached:** `H643_H644_Deep_Analysis_10Jun2026.md`

**What it covers:**  
42m **Hybrid Green Cabin** Fast Crew Boat (hulls H643-H644, job J6257, LR class)

**Hybrid architecture:**
- **4 power sources:** 3× 100 kW gensets + **120 kVA Battery/Grid converter** + 75 kVA shore
- Split-bus MSB with gen/hybrid/shore synchronising
- Operating modes: At Sea (98 kW, 3 gens @ 50% or hybrid converter), Alongside (149 kW shore — **FLAG: shore TX shows 131% loading, exceeds 75 kVA**)

**Distribution tree:**  
MSB → MCC1/PDB1, MCC2, PDB2 (accom/galley), PDB3 (pax deck), PDB4 (bridge/nav), RSDB

**Notable loads:**
- Bow Thruster 75 kW
- **Veem Gyro Stabiliser 35 kW** (roll stabiliser, NOT nav gyro) + dedicated cooling pump + battery charger
- AC condensing 228 kW
- **Battery Room Chiller 15 kW** (hybrid thermal management)
- FiFi pump control
- Galley cooker 5 kW

**Drawings analyzed:**
1. S1156-55-006_A — Electrical Load Analysis Rev A (24/01/2024)
2. S1156-55-005_D — Electrical System SLD Rev D (03/05/2024, 4-source MSB)
3. S1156-55-002_B — Main Switchboard Details Rev B (19/04/2024)
4. J-11132~43 — AMS Working Drawing (Terasaki Mega-Guard, spans H643–49 / H651–56)
5. Terasaki VMS Operator Workstation Manual Rev 1.31 (Nov 2019, 84 pp)

**AMS system:**  
Mega-Guard Ship Automation — high-speed Ethernet 100-BASE-T, redundant network, alarm/monitoring/control with TFT display, EAS operator panel, tag numbering, graphic pages, diagnostics

**Key finding:**  
H643-H644 is **NOT** in the 7-hull audit scope (H640/641/656-659/675) — it's a separate **hybrid family** with battery converter + battery-room chiller. Do NOT cross-copy loads between conventional and hybrid families.

**Open CA:**
- Shore TX 131% alongside-case loading — confirm resolution in Rev B
- AMS working drawing has no text layer — manual indexing required for IO counts

---

## APPS YOU ASKED TO BUILD (Desktop Python Apps)

**Location:** `C:\Users\m_nel\Desktop\Marine_Projects\Marine_Toolkit\`

### App 1: `hull_ingest.py` — Hull Folder Reader & Extractor
**What it does:**  
- Reads entire hull folder (PDFs, Excel, drawings)
- Extracts equipment data → `source_list.xlsx`
- Columns: Tag | Description | kW | V | Phase | Qty | PF | Source Doc | Page
- Flags [MISSING] for blank mandatory fields

**How to run:**  
```bash
python hull_ingest.py --folder "C:\Users\m_nel\Desktop\Marine_Projects\H675"
```

---

### App 2: `workbook_builder.py` — Load List + Alarm List Generator
**What it does:**  
- Input: `source_list.xlsx`
- Output: `Load_List_Rev1.xlsx`, `Alarm_List_Rev1.xlsx`
- Uses H674 template rules
- Locked formulas: 3PH I = P / (√3 × V × 0.85), 1PH I = P / (V × PF)
- Unknowns as [TBC]

**How to run:**  
```bash
python workbook_builder.py --input source_list.xlsx --hull H675
```

---

### App 3: `cable_schedule.py` — IEC 60092-352 Cable Schedule
**What it does:**  
- Input: load list + SLD routing notes
- Output: `Cable_Schedule_Rev1.xlsx`
- IEC 60092-352 sizing (marine cables)
- Lengths marked [TBC] if routing not confirmed

**How to run:**  
```bash
python cable_schedule.py --loadlist Load_List_Rev1.xlsx --sld S1308-55-005.pdf
```

---

### App 4: `research_queue.py` — Resolve [TBC] / [MISSING] via Web Search
**What it does:**  
- Input: any workbook with [TBC], [MISSING], [CA] tags
- Output: web search results with citations, updated workbook
- Example: searches "CAT C7.1 generator datasheet", cites source, fills kW value

**How to run:**  
```bash
python research_queue.py --workbook H675_Load_List_Rev1.xlsx
```

---

### App 5: `folder_organiser.py` — Dedupe, Archive, Auto-Index
**What it does:**  
- Input: hull folder
- Output: `FOLDER_INDEX.md`, `_Archive/` for backups
- Dry-run by default (never deletes)
- Deduplicates file references

**How to run:**  
```bash
python folder_organiser.py --folder "C:\Users\m_nel\Desktop\Marine_Projects\H675"
```

---

## WEB TOOLKIT (Live Website)

**URL:** https://mnelahi-ai.github.io/portfolio/toolkit/  
**Repo:** https://github.com/mnelahi-ai/portfolio

### Calculators (11 tools)

1. **Transformer Short Circuit** (IEC 60909)
2. **Switchboard Rating** (IEC 61439)
3. **Fuel Consumption Estimation**
4. **Motor Earth Fault Current** (NER / solid earthing)
5. **Transformer FLC** (I = kVA / √3 × kV)
6. **Motor FLC + Trip Size** (IEC 60947-4-1)
7. **Cable Volt Drop** (IEC 60092-352, IEC 60364-5-52)
8. **Panel Heat Loss + Ventilation** (IEC 60890)
9. **Earth Cable Adiabatic Sizing** (IEC 60364-5-54: S = I√t / k)
10. **Energy Cost Calculator**
11. **Ex e Enclosure Heat Dissipation** (IEC 60079-7, temperature rise)

### Checklists (12 interactive forms)

- HV Switchgear
- Intake Transformer
- HV/LV Cabling
- LV Transformer
- LV Switchboard
- VSD
- Fire Optic Panel
- Busway
- Emergency Generator
- DC UPS
- Cleanroom
- Power Turn-On (site-based)

**Features:** CSV export, print, auto-date

### Test Forms

- **IR/Megger Test Sheet** with auto pass/fail + printable certificate
- Test voltages per IEC 60092-504

### Reference Tables (6)

1. ANSI protection function codes
2. Motor FLC / trip size lookup
3. XLPE cable parameters (IEC 60092-352)
4. IR test voltages
5. Lux levels (SS 531)
6. Ex marking guide (IEC 60079)

---

## PORTFOLIO STRUCTURE

### Main Portfolio Page
**URL:** https://mnelahi-ai.github.io/portfolio/

**Sections:**
- Hero — Professional identity
- About — 16+ years marine electrical engineering
- Achievements — Fuel burn reduction, IEC 61850 conformity
- Experience — Strategic Marine, Exyte, Phoenix Mecano, Keppel FELS
- Projects — H643-H644 hybrid, offshore wind substation, FPSO
- Core Competencies — Power systems, automation, hybrid energy, safety, modelling
- Emerging & Future-Ready — Cybersecurity, shore power, DC microgrids
- Education & Credentials
- Insights — Thought leadership
- **NEW: Toolkit link** → https://mnelahi-ai.github.io/portfolio/toolkit/
- **NEW: Claude Skills link** → https://mnelahi-ai.github.io/portfolio/claude-skill.html
- **NEW: Apps link** → https://mnelahi-ai.github.io/portfolio/apps.html

---

## FOLDER INDEX

**File attached:** `FOLDER_INDEX.md` (generated 10 Jun 2026)

**Total files indexed:** 7,536 files across:
- 7 hull workbooks (H640, H641, H656-657, H658-659, H661-662, H674, H675)
- Battery library (4 files)
- Cable library (17 approvals)
- Class Rule folder (27 files)
- Equipment datasheets (100+ per hull)
- Drawings (10/15/26/30/35/45/55/65 folders)
- Development files (resumes, cover letters, LinkedIn profiles)
- Standard & Checklist Ref (56 files — FAT, RA, commissioning, lessons learned)

---

## WHAT'S NOW IN YOUR PORTFOLIO

✅ **CLAUDE.md Skill Page** — Published at `/claude-skill.html`  
- Full CLAUDE.md instructions (bullet-point format)
- Hull-specific prompts (H675 Rev6, H656-657 Rev1-B)
- Project deep analysis (H643-H644 hybrid)
- Critical Actions register

✅ **Desktop Apps Page** — Published at `/apps.html`  
- 5 Python apps with install/run instructions
- `hull_ingest.py`, `workbook_builder.py`, `cable_schedule.py`, `research_queue.py`, `folder_organiser.py`
- Example commands
- Requirements: `pip install openpyxl pdfminer.six`

✅ **Marine Electrical Toolkit** — Published at `/toolkit/`  
- 11 calculators
- 12 commissioning checklists
- IR/Megger test forms
- 6 reference tables
- All formulas verified programmatically

✅ **Portfolio Homepage Updated** — New navigation links to Toolkit, Claude Skills, Apps

---

## SUMMARY FOR CLAUDE

When you give this to Claude, it will:

1. **Read `CLAUDE.md` automatically** from `C:\Users\m_nel\AppData\Roaming\Claude\CLAUDE.md`
2. **Know your rules:**
   - Full folder read always
   - Source of truth: `Marine_Electrical_Equipment_List.xlsx`
   - Locked formulas: 3PH PF 0.85, 1PH PF 0.85–0.95
   - No guessing — web-search → cite; not found → flag & stop
   - Auto-tag: [MISSING], [DISCREPANCY], [CA], [TBC]
3. **Generate outputs:**
   - Load List (H674 template)
   - Alarm List (9-group structure)
   - Cable Schedule (IEC 60092-352)
4. **Run the 5 apps** to automate the workflow
5. **Refer to the web toolkit** for calculations, checklists, test forms

---

## GITHUB REPOS

- **Portfolio:** https://github.com/mnelahi-ai/portfolio
- **Marine Toolkit (deprecated, now merged into portfolio):** https://github.com/mnelahi-ai/marine-electrical-toolkit

---

## NEXT STEPS

1. Save this `PORTFOLIO_SUMMARY.md` to `C:\Users\m_nel\Desktop\Marine_Projects\`
2. Copy the bullet-point `CLAUDE.md` (from this summary) to `C:\Users\m_nel\AppData\Roaming\Claude\CLAUDE.md`
3. Restart Claude Desktop — it will read the file automatically
4. Test the 5 Python apps on H675
5. Visit https://mnelahi-ai.github.io/portfolio/ to see everything live

---

**End of Summary**  
**Mashuk Elahi · Marine Electrical Engineer · 11 June 2026**
