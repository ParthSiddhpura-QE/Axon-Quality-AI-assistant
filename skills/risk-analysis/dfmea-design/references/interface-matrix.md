# Interface Matrix — DFMEA Reference

Guide for constructing an interface matrix and boundary diagram for Design FMEA.
Use alongside the [dfmea-design](../SKILL.md) skill.

---

## Why Interfaces Matter

Most design failures occur at **interfaces**, not within a single component.

A component may perform its individual function perfectly, but fail when it interacts with:
- Adjacent components (mechanical contact, electrical connection)
- The environment (temperature, vibration, humidity, corrosion)
- The assembly process (handling forces, fixture contact, torque application)
- The user (loading, misuse scenarios, maintenance access)

An interface matrix maps all these interactions systematically so no failure path is overlooked.

---

## Boundary Diagram

The boundary diagram defines what is **inside** and **outside** the DFMEA scope,
and shows the interfaces at the boundary.

### Elements

**System under analysis (inside scope)**
The component, subsystem, or system being designed.

**External elements (outside scope)**
- Other components in the assembly (customer-supplied or other design teams)
- Environment: thermal, vibration, humidity, electromagnetic, chemical
- User / operator (including misuse scenarios)
- Assembly process (fixtures, torques, handling)
- Maintenance / service (access, tools, replacement cycles)

**Interface arrows**
Draw an arrow for each interaction across the boundary. Label each arrow with:
- The type of interaction (force, signal, thermal, fluid, chemical)
- The nominal condition and range (if known)

### Example — ECU boundary diagram

```
Environment (Temp -40°C to +125°C, vibration 10-2000 Hz)
        ↕
Wiring harness ←→ [ECU] ←→ CAN bus
                    ↕
              Mounting bracket (vibration load transfer)
                    ↕
           Vehicle ground (electrical reference)
```

---

## Interface Matrix — Construction

### Step 1: List all elements

Column and row headers: the component under analysis + all external elements.

### Step 2: Identify interaction type at each intersection

For each pair of elements, identify whether they interact and how.

| Interaction type | Symbol | Examples |
|----------------|--------|---------|
| Force / mechanical | F | Clamping, contact, vibration, thermal expansion |
| Electrical / signal | E | Voltage, current, ground reference, signal |
| Thermal | T | Heat conduction, thermal resistance, temperature delta |
| Fluid / chemical | C | Hydraulic pressure, corrosion medium, lubrication |
| Optical / radiation | O | EMC, light, UV |
| No interaction | — | |

### Example — Connector interface matrix

|  | PCB | Backshell | Wire | Environment | User |
|--|-----|-----------|------|-------------|------|
| **Connector body** | F, E | F | E | T, C | F |
| **Contacts (pins)** | E | — | E | C | — |
| **Sealing** | — | F | F | C | — |

### Step 3: For each interaction, identify failure mode candidates

For each "F", "E", "T", or "C" cell, ask:
- What can go wrong at this interface?
- What is the consequence to the system function?

**Example — Connector body × Environment (T, C):**
- Thermal failure mode: housing deforms under sustained high temperature, contact force lost → intermittent connection
- Chemical failure mode: connector body corrodes in salt spray environment → housing fracture under vibration

These become Failure Modes in Step 4 of the DFMEA.

---

## Interface Failure Mode Patterns

### Mechanical interfaces
| Failure mode | Typical cause |
|-------------|--------------|
| Fretting / wear | Micro-motion under vibration, insufficient clamping force |
| Stress concentration | Geometry (notch, sharp radius), improper tolerance stack-up |
| Thermal expansion mismatch | Dissimilar materials with different CTE |
| Loosening under vibration | Insufficient preload, no locking feature |
| Assembly damage | Handling force exceeds component strength |

### Electrical interfaces
| Failure mode | Typical cause |
|-------------|--------------|
| High contact resistance | Contamination, oxidation, insufficient contact force |
| Signal crosstalk | Insufficient isolation, grounding design |
| Short circuit | Creepage distance insufficient for operating voltage + contamination |
| EMC susceptibility | Shielding gap, ground loop |
| Ground reference drift | High-resistance ground path, shared ground with power |

### Thermal interfaces
| Failure mode | Typical cause |
|-------------|--------------|
| Thermal resistance too high | Poor thermal interface material, insufficient contact area |
| Thermal runaway | Positive feedback loop between power dissipation and junction temperature |
| Condensation | Temperature gradient causes dew point at interface |

### Chemical / environmental interfaces
| Failure mode | Typical cause |
|-------------|--------------|
| Galvanic corrosion | Dissimilar metals in electrolytic environment |
| Seal degradation | Material incompatibility with fluid media |
| Surface finish attack | Wrong coating for environment (salt, humidity, UV) |

---

## Tolerance Stack-Up at Interfaces

When two components interface mechanically, their dimensional tolerances combine.
The worst-case gap or interference is:

```
Worst-case gap     = nominal gap + sum of all tolerance contributions (+ direction)
Worst-case overlap = nominal gap − sum of all tolerance contributions (− direction)
```

**Check for:**
- Minimum clearance at worst-case (prevents binding / assembly interference)
- Maximum clearance at worst-case (prevents slop / rattling / loss of function)
- Special Characteristics on dimensions that directly control an interface

Document the tolerance stack-up analysis in Step 1 (Planning) and reference it in Step 4
when assigning failure modes to interface dimensions.

---

## Interface Matrix → DFMEA Connection

| Interface matrix output | DFMEA field |
|------------------------|------------|
| Element pair with interaction type | Structure Analysis — component and interface level |
| Interface function statement | Function Analysis (Step 3) |
| Failure mode at interface | Failure Mode (Step 4) |
| System consequence of interface failure | Failure Effect (Step 4) |
| Design control that ensures interface performance | Detection control (Step 5) |
| DVP test for interface behaviour | Detection control → DVP entry (Step 6) |

---

## Checklist — Interface Matrix Complete?

- [ ] Boundary diagram drawn — inside and outside scope are clear
- [ ] All external elements identified (adjacent components, environment, user, process)
- [ ] Interface type identified for every element pair that interacts
- [ ] At least one failure mode candidate for every interface cell with an interaction type
- [ ] Tolerance stack-up analysed for all critical mechanical interfaces
- [ ] Interface failure modes transferred to DFMEA Step 4
- [ ] DVP entries exist for all Detection controls at interfaces
