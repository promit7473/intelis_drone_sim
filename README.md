# Intelis Drone Sim

**Meritime Intelligent Drone Sim** — an interactive power / endurance / flight-time model for a Tarot 680 hexacopter, built from general multirotor aerodynamics and anchored to a measured 430 W hover point.

## What it does

- **Momentum-theory rotor model** — hover induced power, profile power, forward-flight inflow (Glauert), parasite drag, climb power.
- **Live energy chain** — capacity → pack mass → all-up weight → thrust → power → endurance → back to the capacity you chose. The original spreadsheet's missing link.
- **Three missions** — Hover (hold a point, which in wind means flying into it), Travelling (one-way endurance), Navigating (climb → outbound → on station → return → descend, with landing reserve).
- **Wind** — live Open-Meteo weather (locks wind speed / direction / temperature only), an animated wind rose you can drag to set the flight track, and a full headwind/tailwind/crosswind decomposition.
- **Discharge rate as a variable** — the pack's continuous C-rating derates usable energy when the flight demands more than it, everywhere in the calculations.
- **Variable audit** — every input is latched through the model; 3 are advisory-only (wheelbase, max thrust, propulsion-table watt cells), 2 are live-weather inputs (lat/lon lookup).

## Key numbers (default build)

- Pack: 10 Ah / 6S, 1298 g, 171 Wh/kg, 80% depth, 5 pt reserve, 95% rate derate
- Hover power ≈ 483 W · best-endurance speed ≈ 12 m/s (23.7 min) · best-range ≈ 18.8 m/s
- Hover endurance ≈ 18.4 min in still air

## Files

- `flight-time-model.html` — the entire simulator (self-contained, no build step). Open in a browser.
- `Copy of Hexacopter price list - Power Calculation.pdf` — the original worksheet the model critiques in §7.
