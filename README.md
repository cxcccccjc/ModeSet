# ModeSet

**ModeSet: Compositional Truth Discovery Against Recurrent Coordinated Poisoning**

This repository distributes the complete experimental source and reproducibility resources in [ModeSet_Source.zip](ModeSet_Source.zip). The archive contains the implementations, fixed experiment configurations, public sensor inputs used in the paper, per-seed results, statistical export, verification scripts, and the scripts for experimental Figures 5--11.

## Download and run

Download and extract `ModeSet_Source.zip`, then enter its `ModeSet` directory. Use Python 3.12:

```bash
python -m pip install -r requirements.txt
python verify_and_replay.py --quick
```

The representative check covers eight replayed records, all 556 summary rows, and 100 set-geometry instances. The release preserves 3,846 current-paper per-seed records. Original estimators, inputs, and numerical records are unchanged.

A new single trial:

```bash
python run_current_experiments.py --phase main --method ModeSet --dataset syn --limit 1 --output derived/trial_001
```

The complete current experiment suite and summary:

```bash
python run_current_experiments.py --all --workers 3 --output derived/full_001
python export_current_selection.py --source derived/full_001 --output derived/full_001_summary
```

Experimental Figures 5--11:

```bash
python -m pip install -r figures/requirements.txt
python figures/plot_experiment_panels.py
```

The archive's `README.md` provides the complete source map, experiment filters, and diagnostics. `docs/BASELINES.md` identifies calibration controls, structural variants, and literature-derived numerical cores; these adaptations do not claim to implement complete cryptographic or network protocols. `docs/DATA_SOURCES.md` documents UCI data attribution and the included subset. `docs/FIGURES.md` documents plotting and optional Chinese fonts.

## Scope

ModeSet combines learned source-specific recurrent states to recover truth under coordinated poisoning and changing environmental values. The sensor experiments use public measured reports with injected attacks. Theoretical results use the assumptions in the supplementary material; empirical MAD radii are not unconditional confidence intervals.

Numerical requirements are fixed in `requirements.txt`. The reference environment is Python 3.12.14 and NumPy 2.3.5. Rebuilding figures was verified with Matplotlib 3.11.2. No manuscript PDF, author photograph, credential, bundled interpreter, or typesetting engine is included.
