# 🤖 UV Air Purifier Bot

An autonomous mobile robot that combines **HEPA filtration** and **UV-C air disinfection** to clean indoor air more effectively than stationary purifiers — by seeking out stagnant zones where pollutants accumulate.

---

## 🎯 Project Goal

Prove that a **moving air purifier** cleans a room faster and more thoroughly than a stationary one, especially in dead zones (corners, under desks, behind furniture) where air is most stagnant.

---

## 🧪 Science Behind It

### UV-C Disinfection
UV-C light (200–280 nm) damages bacterial and viral DNA/RNA, stopping reproduction. It does **not** penetrate human skin, making it the safest UV band for enclosed use.

**Dosage Formula:**
```
Dosage (mJ/cm²) = Intensity (mW/cm²) × Time (s)
```
- Target pathogen: spores → require **20–50 mJ/cm²**
- Target exposure time: **~2 seconds**
- Required intensity: **> 12.5 mW/cm²**

### Why UV Alone Isn't Enough
UV disables pathogens but doesn't capture them. A **HEPA filter** is required to physically trap particles. UV acts as a secondary sterilization layer.

### Why the Robot Needs to Move
Rooms have **dead zones** — corners, under furniture — where air is naturally stagnant. A stationary purifier cleans air near itself much faster than in these zones. The robot identifies and targets these areas.

---

## 📁 Repo Structure

```
uv-purifier-bot/
├── README.md
├── docs/
│   ├── safety.md          # UV safety, electrical safety, motion safety
│   ├── design-specs.md    # Component specs and system design
│   └── inspiration.md     # Prior art and existing designs
├── experiments/
│   ├── experiment-1.md    # Stationary purifier stagnant zone test
│   └── data/              # Raw sensor readings
├── design/
│   └── system-overview.md # Airflow design, UV chamber layout
└── hardware/
    └── bom.md             # Bill of materials / parts list
```

---

## 🔬 Experiments

| # | Question | Status |
|---|----------|--------|
| 1 | Does a stationary HEPA purifier clean stagnant zones effectively? | ✅ Complete |
| 2 | Does centralized AC clean air as effectively as a HEPA purifier? | ⬜ Planned |
| 3 | Does a moving purifier outperform stationary in overall room cleaning? | ⬜ Planned |

---

## ⚠️ Safety First

- UV-C is **never exposed** directly — enclosed in the air duct at all times
- Plastic casing absorbs stray UV-C
- Temperature sensors on UV lamp to prevent overheating
- Fuses and overcurrent limiters on all electrical circuits
- Robot moves slowly with obstacle detection sensors

See [`docs/safety.md`](docs/safety.md) for full details.

---

## 🛒 Key Components

| Component | Spec |
|-----------|------|
| UV-C Lamp | 254 nm, ≥25W |
| Fan | CFM 350–400 |
| Filter | HEPA |
| Air quality sensor | PM2.5 |
| Target robot volume | ~0.5 m³ |

See [`hardware/bom.md`](hardware/bom.md) for full parts list.
