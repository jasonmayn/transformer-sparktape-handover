# TRANSFORMER — SparkTape evidence manifest

Read-only export list. Source tree: `/workspace/artifacts/projects/Sparktape`.
Nothing here was modified. SHA-256 sidecars were checked against the adjacent file bytes: 17/17 matched.
No secrets, API keys, or private credentials were found in the Python sources. Public RPC URLs are not secrets, but they are operational defaults, not credentials.

Classes:

- `EXPORT_SMALL` — enough to verify frozen conclusions and hashes.
- `EXPORT_CODE` — semantics. Copy only if TRANSFORMER will read rules, not just results. Exclude `__pycache__`.
- `EXPORT_RAW_ON_DEMAND` — large tapes. Do not include in the small package. Do not inspect quarantined outcomes.
- `DO_NOT_EXPORT_AS_EVIDENCE` — present, but not a scientific result or not safe to treat as one.

## EXPORT_SMALL

| Bytes | Path |
|---:|---|
| 7741 | `data/sparktape_activity_stasis_prereg_v1.json` |
| 1790 | `data/sparktape_activity_stasis_v1_closure.json` |
| 309660 | `data/sparktape_activity_stasis_v1_estimation.json` |
| 547873 | `data/sparktape_activity_stasis_v1_prospective_1000.json` |
| 459026 | `data/sparktape_activity_stasis_v1_prospective_manifest.json` |
| 7004 | `data/sparktape_buyer_renewal_prereg_v1.json` |
| 2291 | `data/sparktape_buyer_renewal_v1_closure.json` |
| 68379 | `data/sparktape_buyer_renewal_v1_primary_analysis.json` |
| 199935 | `data/sparktape_buyer_renewal_v1_prospective_500.json` |
| 219000 | `data/sparktape_buyer_renewal_v1_prospective_manifest.json` |
| 10487 | `data/sparktape_distribution_risk_prereg_v1.json` |
| 114 | `data/sparktape_distribution_risk_prereg_v1.json.sha256` |
| 2349 | `data/sparktape_distribution_risk_v1_closure.json` |
| 115 | `data/sparktape_distribution_risk_v1_closure.json.sha256` |
| 91941 | `data/sparktape_distribution_risk_v1_primary_analysis.json` |
| 124 | `data/sparktape_distribution_risk_v1_primary_analysis.json.sha256` |
| 287301 | `data/sparktape_distribution_risk_v1_prospective_500.json` |
| 287254 | `data/sparktape_distribution_risk_v1_prospective_manifest.json` |
| 7241 | `data/sparktape_dormancy_hazard_prereg_v1.json` |
| 2631 | `data/sparktape_dormancy_hazard_v1_prospective_manifest.json` |
| 10964 | `data/sparktape_replacement_demand_prereg_v1.json` |
| 115 | `data/sparktape_replacement_demand_prereg_v1.json.sha256` |
| 2084 | `data/sparktape_replacement_demand_v1_closure.json` |
| 105293 | `data/sparktape_replacement_demand_v1_primary_analysis.json` |
| 517645 | `data/sparktape_replacement_demand_v1_prospective_1000.json` |
| 227242 | `data/sparktape_replacement_demand_v1_prospective_500.json` |
| 510519 | `data/sparktape_replacement_demand_v1_prospective_manifest.json` |
| 12424 | `data/sparktape_risk_fence_prereg_v1_outcome_addendum.json` |
| 124 | `data/sparktape_risk_fence_prereg_v1_outcome_addendum.json.sha256` |
| 10046 | `data/sparktape_risk_fence_prereg_v1_same_slot_toxicity.json` |
| 126 | `data/sparktape_risk_fence_prereg_v1_same_slot_toxicity.json.sha256` |
| 13498 | `data/sparktape_risk_fence_prereg_v2_same_slot_toxicity_canonical.json` |
| 136 | `data/sparktape_risk_fence_prereg_v2_same_slot_toxicity_canonical.json.sha256` |
| 2283 | `data/sparktape_risk_fence_v1_closure.json` |
| 108 | `data/sparktape_risk_fence_v1_closure.json.sha256` |
| 401555 | `data/sparktape_risk_fence_v1_prospective_1000.json` |
| 177043 | `data/sparktape_risk_fence_v1_prospective_500.json` |
| 401082 | `data/sparktape_risk_fence_v1_prospective_manifest.json` |
| 2601 | `data/sparktape_risk_fence_v2_closure.json` |
| 108 | `data/sparktape_risk_fence_v2_closure.json.sha256` |
| 9811 | `data/sparktape_risk_fence_v2_primary_analysis.json` |
| 117 | `data/sparktape_risk_fence_v2_primary_analysis.json.sha256` |
| 186680 | `data/sparktape_risk_fence_v2_prospective_500.json` |
| 186633 | `data/sparktape_risk_fence_v2_prospective_manifest.json` |
| 10125 | `data/sparktape_sell_shock_replenishment_prereg_v1.json` |
| 2300 | `data/sparktape_sell_shock_replenishment_v1_closure.json` |
| 88287 | `data/sparktape_sell_shock_replenishment_v1_estimation.json` |
| 336399 | `data/sparktape_sell_shock_replenishment_v1_prospective_500.json` |
| 397458 | `data/sparktape_sell_shock_replenishment_v1_prospective_manifest.json` |
| 26011 | `data/strategy_c_prereg_v1.json` |
| 1372 | `data/strategy_c_prereg_v1_closure.json` |
| 79150 | `data/strategy_c_prereg_v1_dev_baseline.jsonl` |
| 407 | `data/strategy_c_prereg_v1_dev_baseline_summary.json` |
| 7424 | `data/strategy_c_prereg_v1_dev_feature_analysis.json` |
| 116799 | `data/strategy_c_prereg_v1_dev_secondary_baselines.jsonl` |
| 787 | `data/strategy_c_prereg_v1_dev_secondary_summary.json` |
| 595 | `data/strategy_c_prereg_v1_feature_semantics_note.json` |
| 2213 | `data/strategy_c_prereg_v2_closure.json` |
| 105 | `data/strategy_c_prereg_v2_closure.json.sha256` |
| 1330 | `data/strategy_c_prereg_v2_washout_reclaim.json` |
| 2560 | `data/strategy_c_prereg_v3_closure.json` |
| 105 | `data/strategy_c_prereg_v3_closure.json.sha256` |
| 7959 | `data/strategy_c_prereg_v3_momentum_restart.json` |
| 114 | `data/strategy_c_prereg_v3_momentum_restart.json.sha256` |
| 72060 | `data/strategy_c_v2_prospective_300.json` |
| 101 | `data/strategy_c_v2_prospective_300.json.sha256` |
| 166810 | `data/strategy_c_v2_prospective_500.json` |
| 106 | `data/strategy_c_v2_prospective_500.json.sha256` |
| 146602 | `data/strategy_c_v2_prospective_manifest.json` |
| 58836 | `data/strategy_c_v3_execution_gate_audit.json` |
| 111 | `data/strategy_c_v3_execution_gate_audit.json.sha256` |
| 4108 | `data/strategy_c_v3_execution_gate_correction.json` |
| 227799 | `data/strategy_c_v3_prospective_500.json` |
| 106 | `data/strategy_c_v3_prospective_500.json.sha256` |
| 200383 | `data/strategy_c_v3_prospective_manifest.json` |
| 551 | `data/dual_feed_engineering/artificial_gap_schedule.json` |
| 12356 | `data/dual_feed_engineering/canonical_backfill_validation.json` |
| 8414 | `data/dual_feed_engineering/gap_reconstruction_validation.json` |
| 1488 | `data/dual_feed_engineering/validation_summary.json` |
| 2804 | `data/sparktape_dormancy_hazard_v1_collection_deviation_20261022.json` |
| 1735 | `data/sparktape_dormancy_hazard_v1_implementation_note.json` |
| 1541 | `data/sparktape_dormancy_hazard_v1_session_exclusion_dh1-20261016-202016.json` |

Also export these non-data files with the small package:

- `README.md` (999 bytes)
- `requirements.txt` (34 bytes)
- `deploy/SPARKTAPE_RUNNER_DEPLOY.md` (4311 bytes)
- `deploy/runner_bundle_file_hashes.json` (3184 bytes)
- `deploy/sparktape-dormancy-runner-bundle-v1-status.json` (284 bytes)

## EXPORT_CODE

All `*.py` at the SparkTape root, `tests/test_*.py`, `tests/fixtures/pump_live/*.json`, `idl/pump.json`, and the systemd units in `deploy/`.

Counted: 65 root Python modules, 37 test modules, IDL `idl/pump.json`.

Do not export `__pycache__` or `*.pyc`. Bytecode is not a test result.

## EXPORT_RAW_ON_DEMAND

Directories under `data/session_archives/`. Part files are 128MB class. Not hashed again for this manifest.

- `data/session_archives/dh1-20261016-202016/` EXCLUDED. Completeness audit fail. Contributes 0.
- `data/session_archives/dh1-20261020-102656/`
- `data/session_archives/dh1-20261022-041357/`
- `data/session_archives/dh1-20261022-045654/` QUARANTINED. Do not unpack to inspect outcomes.
- `data/session_archives/st02-20261006-232348/`
- `data/session_archives/st03-20261011-222617/`
- `data/session_archives/st05-20261014-004213/`
- `data/session_archives/st05-20261014-070602/`
- `data/session_archives/st07-20261012-103723/`
- `data/session_archives/st07-20261012-210616/`

Study session directories (already-finalized JSON lives inside; prefer the `data/*.json` milestones over re-deriving):

- `data/strategy_c_v2_sessions/`
- `data/strategy_c_v3_sessions/`
- `data/sparktape_risk_fence_v1_sessions/`
- `data/sparktape_risk_fence_v2_sessions/`
- `data/sparktape_distribution_risk_v1_sessions/`
- `data/sparktape_replacement_demand_v1_sessions/`
- `data/strategy_c_sessions/`
- `data/strategy_c_archive/`

## DO_NOT_EXPORT_AS_EVIDENCE

- `data/control_v1_paper.json` — early paper book, 1 open and 53 closed as of 2026-10-02 08:06:52 UTC. Not tied to a closure.
- `data/out/scan_20260928_*` — Era A desk scans. Not a preregistered cohort.
- `data/ohlcv/` — three token files. Not cited by a closure.
- `__pycache__/` anywhere.
- `deploy/sparktape-dormancy-runner-bundle.tar` and `...-v2.tar` — built bundles. The deploy markdown and `runner_bundle_file_hashes.json` are the readable contract. The v2 tar was not opened for this handover.
- Any file whose only role is a V1 holdout slice. No such filename was found. If a later reader finds holdout rows inside a tape, leave them unread.

## Integrity already checked

17/17 `data/*.sha256` sidecars match the adjacent bytes.
Closure-cited milestone and primary-analysis hashes that were re-read also matched, including ST-01, ST-02, ST-03, ST-05, ST-07, Risk Fence v2, Strategy C v2 milestones 300 and 500, and Strategy C v3 milestone 500 plus the execution-gate audit.
Control A hash `485e604389d4c04d9785600d8e48b4095fbb225bf407b82927ea8c3d58091292` and Control B hash `cf7d2065aa644c97ebcb1118bbd2d7657b54d6de5f19bafdf4a37029b3b246f0` are recorded in closures only. The files were not isolated.

Original Grok transcript: not in this workspace. Do not invent it.
