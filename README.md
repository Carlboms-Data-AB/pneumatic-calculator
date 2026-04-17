# Pneumatic Cylinder Calculator

A single-file, browser-based calculator for sizing and analyzing double-acting pneumatic cylinders. No build step, no dependencies — just open `index.html`.

## Features

- **Cylinder geometry** — set bore `D` and rod `d` manually, or pick an ISO 15552 preset (Ø32 up to Ø320). Live display of cap-side area, rod-side area, and area ratio.
- **Force calculator** — compute theoretical and effective force for extension or retraction, given cap-side and rod-side pressures.
- **Required pressure** — enter a target force and one known pressure; solves for the missing one.
- **Bore sizing** — given a target force and available supply pressure, returns the minimum bore and suggests the next ISO 15552 size (uses standard ISO rod diameters for retraction).
- **Air consumption** — free air per double stroke and per minute, using Boyle's law and atmospheric reference 1.01325 bar.
- **Unit support** — pressure (bar, psi, kPa, MPa), length (mm, cm, in), force (N, kN, lbf, kgf). Each field has its own unit dropdown.
- **Friction loss** — global friction percentage (0–50%) applied to effective force and to required-pressure solves.

## Usage

Hosted at **<https://cylindercalc.carlbomsdata.se>**. All calculations run client-side; nothing is sent anywhere.

## Formulas

- Cap-side area: `A_cap = π/4 · D²`
- Rod-side area: `A_rod = π/4 · (D² − d²)`
- Extension force: `F = P_a · A_cap − P_b · A_rod`
- Retraction force: `F = P_b · A_rod − P_a · A_cap`
- Effective force: `F_eff = F_theoretical · (1 − friction)`
- Free air per stroke: `V_free = A · stroke · (P_supply + P_atm) / P_atm`

Pressure is converted to N/mm² internally (1 bar = 0.1 N/mm²) so force comes out in newtons when areas are in mm².

## Disclaimer

Results are for estimation and engineering preview only. Always verify against manufacturer datasheets and applicable standards before specifying real hardware.

## License

See [LICENSE](LICENSE).
