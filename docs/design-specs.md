# 🔧 Design Specifications

## System Overview

The robot integrates a HEPA filter and UV-C sterilization chamber into a mobile autonomous platform. Air is drawn in from the top, passes through the UV-C chamber, then through the HEPA filter, and is exhausted out the side.

```
        ┌──────────────┐
        │  AIR INTAKE  │  ← Top of robot
        └──────┬───────┘
               │
        ┌──────▼───────┐
        │  UV-C CHAMBER│  ← Lamp 2–5 cm from duct wall
        │  (254 nm)    │     Exposure time: ~2 seconds
        └──────┬───────┘
               │
        ┌──────▼───────┐
        │ HEPA FILTER  │  ← Captures particles disabled by UV
        └──────┬───────┘
               │
        ┌──────▼───────┐
        │  AIR EXHAUST │  ← Side wall, far from intake
        └──────────────┘
```

## UV-C Dosage Calculations

| Parameter | Value |
|-----------|-------|
| Target pathogen | Spores |
| Required dosage | 20–50 mJ/cm² (target: 25) |
| Target exposure time | 2 seconds |
| Required lamp intensity | > 12.5 mW/cm² |
| Lamp wavelength | 254 nm |
| Minimum lamp wattage | 25W |

## Fan Specifications

- **Target CFM:** 350–400
- Fan must be strong enough to pull air from stagnant high zones
- Must allow ~2 second dwell time in UV-C chamber per air batch

## Robot Physical Specs

| Parameter | Target Value |
|-----------|--------------|
| Volume | ~0.5 m³ |
| Air intake | Top of unit |
| Air exhaust | Side wall |
| UV lamp distance from wall | 2–5 cm |

## UV Source Options

### Option A: UV Lamp (Selected)
- ✅ High intensity — can meet dosage requirements
- ✅ Lower cost
- ❌ Fragile
- ❌ Contains mercury — disposal considerations

### Option B: UV LEDs
- ✅ Safer, no mercury
- ✅ Longer lifespan
- ❌ Much lower intensity — requires longer exposure time
- ❌ More expensive for equivalent output

**Decision: UV Lamp** selected for proof-of-concept due to intensity requirements.

## Airflow Design Principles

- Air always takes the path of least resistance — entrance and exit must be on opposite walls and maximally separated.
- Avoid short pathways that bypass the UV exposure zone.
- Plastic duct walls absorb stray UV-C, protecting the outer environment.
