# Data Package Manifest

This repository is a compact public release package for a 1920-case electrical cabinet fault simulation dataset. It is designed for GitHub distribution: code, case definitions, summary tables, and small representative examples are included; large raw per-case training artifacts are excluded.

## Included

| Path | Contents |
| --- | --- |
| `cabinet_fault_simulation/` | Simulation package and configuration tables. |
| `scripts/` | Reproducibility, calibration-demo, validation, and audit scripts. |
| `case_definitions/` | Complete 1920-case definitions and split manifest. |
| `results_summary/` | Case-level simulation summary table. |
| `data_examples/simulation_examples/` | Small raw simulation examples copied from the original per-case outputs. |
| `data_examples/source_domain_examples/` | Placeholder for permitted source-domain or calibration examples. No unreleased source-domain data are included by default. |
| `docs/` | Notes describing how external experimental/literature evidence constrains calibration. |

## Representative Simulation Examples

The example cases use the original per-case `system_timeseries.csv.gz` files.

Included cases:

| Case | Purpose |
| --- | --- |
| `CASE_00001` | Low-current no-fire example. |
| `CASE_00379` | KM1_DC ignition example. |
| `CASE_00427` | KM1_DC high-intensity ignition example. |
| `CASE_00907` | KM1_AC ignition example. |
| `CASE_01184` | X1 ignition example. |
| `CASE_01500` | X2 low-current no-fire example. |
| `CASE_01800` | X2 aged ignition example. |
| `CASE_01869` | X2 high-current ignition example. |

Each example case contains:

| File | Description |
| --- | --- |
| `case_config.json` | Case configuration. |
| `summary.json` | Per-case summary. |
| `diagnostics.csv` | Tabular diagnostic outputs. |
| `diagnostics.json` | Diagnostic metadata. |
| `system_timeseries.csv.gz` | Raw compressed system time series from the original simulation output. |

Large files such as `pigat_data.npz` and `history.csv.gz` are intentionally not included in this GitHub package.

## Excluded

| Excluded item | Reason |
| --- | --- |
| Full 1920-case raw output tree | Too large for a practical GitHub repository. |
| `CASE_*/pigat_data.npz` | Large downstream training artifact. |
| `CASE_*/history.csv.gz` | Large detailed history export; not needed for the compact public package. |
| Virtual environments | Reproducibility should use `requirements.txt`. |
| Logs, process IDs, Python cache, backup files | Runtime or local development artifacts. |

## Source-Domain Data Policy

The repository may include small, representative source-domain or calibration examples when they are approved for public release. If source-domain data cannot be released, document the restriction and provide the preprocessing format expected by the calibration workflow.


