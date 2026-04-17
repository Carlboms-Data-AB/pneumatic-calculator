# Pneumatic Cylinder Calculator

Browser-based calculator for double-acting pneumatic cylinders. Live at **<a href="https://cylindercalc.carlbomsdata.se" target="_blank" rel="noopener">cylindercalc.carlbomsdata.se</a>**.

## What it does

- **Force** — theoretical and effective force for extension or retraction.
- **Required pressure** — target force + one known pressure → the missing pressure.
- **Bore sizing** — target force + supply pressure → minimum bore, with next ISO 15552 size.
- **Air consumption** — free air per cycle and per minute.

Supports bar/psi/kPa/MPa, mm/cm/in, N/kN/lbf/kgf, ISO 15552 presets (Ø32–Ø320), and a friction-loss percentage.

## Formulas

- Cap-side area: `A_cap = π/4 · D²`
- Rod-side area: `A_rod = π/4 · (D² − d²)`
- Extension force: `F = P_a · A_cap − P_b · A_rod`
- Retraction force: `F = P_b · A_rod − P_a · A_cap`
- Effective force: `F_eff = F_theoretical · (1 − friction)`
- Free air per stroke: `V_free = A · stroke · (P_supply + P_atm) / P_atm`

## Disclaimer

For estimation only. Verify against manufacturer datasheets before specifying real hardware.

## License

See [LICENSE](LICENSE).
