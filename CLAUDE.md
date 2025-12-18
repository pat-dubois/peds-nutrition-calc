# Pediatric Nutrition Calculator

**Purpose:** A surprise gift for Crystal - a web-based tool to calculate pediatric nutrition requirements (energy, protein, fluid) for her work at Jim Pattison Children's Hospital.

**Status:** In Development

---

## What This Project Does

Replaces error-prone Excel spreadsheets with a fast, reliable, mobile-friendly calculator for pediatric dietitians and clinicians.

**Inputs:**
- Weight (kg)
- Height (cm)
- Age (years + months)
- Gender (Male/Female)
- Activity Level (Sedentary, Low Active, Active, Very Active)

**Outputs:**
- Energy Requirement (kcal/day)
- Protein Requirement (g/day)
- Fluid Requirement (mL/day)

Each output includes a "Show Your Work" toggle to display the actual calculation.

---

## Formula Sources

### Energy (EER) - Health Canada DRIs

**Infants 0-35 months:**
- 0-3 mo: `(89 × weight_kg - 100) + 175`
- 4-6 mo: `(89 × weight_kg - 100) + 56`
- 7-12 mo: `(89 × weight_kg - 100) + 22`
- 13-35 mo: `(89 × weight_kg - 100) + 20`

**Children 3-18 years:**
- Boys 3-8y: `88.5 - (61.9 × age) + PA × [(26.7 × weight_kg) + (903 × height_m)] + 20`
- Boys 9-18y: `88.5 - (61.9 × age) + PA × [(26.7 × weight_kg) + (903 × height_m)] + 25`
- Girls 3-8y: `135.3 - (30.8 × age) + PA × [(10.0 × weight_kg) + (934 × height_m)] + 20`
- Girls 9-18y: `135.3 - (30.8 × age) + PA × [(10.0 × weight_kg) + (934 × height_m)] + 25`

**PA Coefficients:**
| Activity Level | PA Value |
|----------------|----------|
| Sedentary      | 1.0      |
| Low Active     | 1.11     |
| Active         | 1.25     |
| Very Active    | 1.48     |

### Protein - Health Canada DRIs (RDA g/kg/day)

| Age Group    | g/kg/day |
|--------------|----------|
| 0-6 months   | 1.52     |
| 7-12 months  | 1.2      |
| 1-3 years    | 1.05     |
| 4-8 years    | 0.95     |
| 9-13 years   | 0.95     |
| 14-18 years  | 0.85     |

### Fluid - Holliday-Segar Formula (1957)

- First 10 kg: 100 mL/kg/day
- Next 10 kg (11-20 kg): 50 mL/kg/day
- Each kg > 20 kg: 20 mL/kg/day

---

## Technical Stack

- **Single HTML file** with embedded CSS and JavaScript
- **No dependencies** - works anywhere, no build process
- **Hosting:** GitHub Pages

---

## Project Files

```
pedes-app/
├── index.html      # The complete app
├── CLAUDE.md       # This file
├── README.md       # User documentation
└── test-cases.md   # Validation test cases
```

---

## Key Design Decisions

1. **Single HTML file:** Maximum portability, Crystal can even save it locally
2. **Years + Months age input:** Intuitive for clinical use
3. **Show Your Work:** Builds trust, proves no hallucinations
4. **Mobile-first:** Crystal moves between patients
5. **Jim Pattison-inspired colors:** Professional, familiar

---

## Validation Reference

The Baylor College of Medicine calculator (https://www.bcm.edu/cnrc-apps/bodycomp/bmiz3.html) can be used to cross-validate energy calculations.

---

## Future Enhancements (v2+)

- Pencil animation for "show your work"
- Gus the dog sprite as signature
- Print/PDF export
- Adult calculator
- PWA for offline use
- COPY toggle that copies the results to the clipboard nicely formatted

---

## Session Status (2025-12-17)

### What Was Accomplished
- Built complete Pediatric Nutrition Calculator from scratch
- Researched and implemented Health Canada DRI formulas (energy, protein)
- Implemented Holliday-Segar fluid formula
- Created "Show Your Work" feature for calculation transparency
- Designed mobile-responsive UI with Jim Pattison Children's Hospital-inspired colors
- Added dark mode with persistent toggle
- Deployed to GitHub Pages: https://pat-dubois.github.io/peds-nutrition-calc/
- Created test-cases.md with 5 validated calculation scenarios
- Made first public GitHub repo

### Next Session TODO
1. Have Crystal validate calculations against real patient data
2. Send her the link as the surprise
3. Consider v2 enhancements: Gus sprite, pencil animation, copy-to-clipboard