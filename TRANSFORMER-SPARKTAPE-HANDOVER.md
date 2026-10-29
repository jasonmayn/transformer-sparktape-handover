# TRANSFORMER — SparkTape handover

Read-only. Prepared 2026-10-29 from the saved tree at `/workspace/artifacts/projects/Sparktape`. SparkTape was not modified. No service was restarted. No study was reopened. No test was rerun. No live RPC call was made.

## Evidence classes

| Class | Meaning in this document |
|---|---|
| VERIFIED FILE | The file is in the saved tree and was read, or its SHA-256 was checked against a stored sidecar or a closure citation. |
| FILE PRESENT, NOT RECOMPUTED | The file exists. Counts below are the numbers stored in a closure, milestone, or audit JSON. The statistic was not recalculated. |
| RECORDED HASH ONLY | A SHA-256 is stored in a closure. The matching bytes were not isolated in this pass. |
| UNAVAILABLE | Not in this workspace. Not inferred. |

The original Grok conversation transcript is **UNAVAILABLE**. No chat log, export, or transcript file for SparkTape was found. There is also no git repository inside the tree. A stored V3 audit field says `git_repository: False`. GitHub account `jasonmayn` has no SparkTape repository. Anything that used to live only in the chat, and not in these files, is gone.

No API keys or private credentials were found in the Python sources. Public endpoints are listed because they are hardcoded defaults, not secrets.

## 1. Purpose, architecture, and what is actually distinctive

SparkTape is two eras in one directory.

**Era A — attention desk.** `sparktape.py` and `README.md` describe a new-pair / paid-heat scanner. It polls DexScreener, checks GoPlus, and optionally GeckoTerminal. Paid boosts are labeled `PAID_HEAT`, not `SPARK`. Tags are `SPARK`, `WATCH`, `PAID_HEAT`, `SKIP_RUG`, `SKIP_THIN`, `FLAT`. The README calls it a sister desk to Crowdtape and says it does not buy. This era is not the later scientific program.

**Era B — Pump.fun research program.** Almost all of the Python and `data/` JSON is a frozen-protocol research system on Pump.fun bonding-curve launches. It records chain events, censors socket gaps, and scores preregistered hypotheses. The collectors are written to refuse buys. Strategy C closures record `strategy_c_buys: 0`.

What is distinctive, and verified from module docstrings plus the frozen JSON:

- Gap is not treated as a quiet market (`coverage.py`).
- Live receipt time, Pump event time, and canonical chain order are separate clocks. Chain order is slot, transaction index, then program-data index. Websocket receipt time does not overwrite chain time.
- HTTP `getBlock` backfill is historical reconstruction. It is not allowed to promote a live gap into a live-complete window.
- Studies are closed by a written classification. A negative or opposite result is not turned into a production fence. The V1 holdout is recorded as unopened in every closure that mentions it.
- Signature-cache fill is separated from scientific finalization. The dormancy runner has no finalize, Cox, trading, or delete command.

Logical layout:

| Layer | Modules |
|---|---|
| Desk scanner | `sparktape.py`, `collector.py` |
| Decode | `pump_decode.py`, `idl/pump.json` (`pump-idl-2026-10-02`) |
| Live logs | `chain_live.py`, `measure_chain.py`, `chain_tape.py`, `chain_v2.py`, `chain_checkpoints.py` |
| Coverage and reconstruction | `coverage.py`, `dual_coverage.py`, `dual_backfill.py`, `gap_reconstruction.py`, `canonical_state.py`, `canonical_validation.py` |
| Paper execution semantics, no orders | `outcome_v1.py`, `curve_quote.py`, `quote_normalization.py`, `execution_gate_semantics.py`, `v2_path.py`, `v3_path.py` |
| Closed or frozen studies | `distribution_risk*.py`, `replacement_demand*.py`, `buyer_renewal*.py`, `risk_fence*.py`, `st05_sell_shock.py`, `st07_activity.py`, `dormancy_hazard*.py` |
| Operations | `sparktape_runner.py`, `session_spool.py`, `checkpoint_writer.py`, `checkpoint_dormancy_sigcache.py`, `deploy/` |

`session_spool.py` says hot writes must not touch the FUSE project folder. `deploy/SPARKTAPE_RUNNER_DEPLOY.md` says sessions, jobs, logs, and checkpoints must not live in `/tmp`.

## 2. Source and dataset locations

| What | Where | Status |
|---|---|---|
| Only source tree found | `/workspace/artifacts/projects/Sparktape` | VERIFIED FILE |
| IDL | `idl/pump.json` | VERIFIED FILE present (268,716 bytes). Not re-decoded. |
| Frozen conclusions | `data/*closure.json`, `data/*prereg*.json` | VERIFIED FILE |
| Prospective milestones and primary analyses | `data/*prospective*.json`, `data/*primary_analysis.json`, `data/*estimation.json` | FILE PRESENT. Hashes cited by closures were checked where noted below. |
| Raw session chunks | `data/session_archives/<session>/` | FILE PRESENT. Multi-hundred-MB part files. Not unpacked and not re-hashed for this handover. |
| Early desk outputs | `data/out/` (24 CSV, 25 JSON, one cron log, one nohup) | FILE PRESENT, NOT RECOMPUTED |
| Early paper book | `data/control_v1_paper.json` | FILE PRESENT. 1 open, 53 closed. `updated` field is `2026-10-02 08:06:52 UTC`. Not re-scored. Not identified as Control A or Control B. |
| Small chain scratch | `data/chain_raw.jsonl` | VERIFIED FILE. 124 lines, 152,937 bytes. |
| Dependencies | `requirements.txt` | `websockets>=13,<14` and `base58>=2.1,<3` only. |

No upstream git remote, no original workstation path, and no live runner host are in this tree. The deploy note assumes a future copy under `$HOME/sparktape-runner`. That home directory is not here.

## 3. Completed phases

These are file-backed. They are not a reconstruction of the chat.

**Desk scans.** `data/out/scan_20260928_*.json` and matching CSV files exist. They were not re-audited.

**Engineering, not cohorts.**

- Dual-feed check `dual-20261005-222329`, about 601.5 seconds. Stored in `data/dual_feed_engineering/validation_summary.json`.
- Artificial-gap reconstruction session `gap-20261005-230222`. Two stored verdicts, described in section 6. Both files say they are not a scientific cohort.

**Strategy C, newborn-long family.** Closed as a family. See section 4.

**ST studies on later prospective tapes.**

| ID | Protocol file | Closure file | Classification stored in the closure |
|---|---|---|---|
| ST-01 | `sparktape_distribution_risk_prereg_v1.json` | `sparktape_distribution_risk_v1_closure.json` | `CLOSED_HYPOTHESIS_NOT_SUPPORTED` |
| ST-02 | `sparktape_replacement_demand_prereg_v1.json` | `sparktape_replacement_demand_v1_closure.json` | `CLOSED_HYPOTHESIS_NOT_SUPPORTED` |
| ST-03 | `sparktape_buyer_renewal_prereg_v1.json` | `sparktape_buyer_renewal_v1_closure.json` | `CLOSED_HYPOTHESIS_NOT_SUPPORTED` |
| Risk Fence v1 | `sparktape_risk_fence_prereg_v1_same_slot_toxicity.json` plus outcome addendum | `sparktape_risk_fence_v1_closure.json` | `CLOSED_TOO_IMBALANCED_FOR_PREREGISTERED_COMPARISON` |
| Risk Fence v2 | `sparktape_risk_fence_prereg_v2_same_slot_toxicity_canonical.json` | `sparktape_risk_fence_v2_closure.json` | `CLOSED_HYPOTHESIS_NOT_SUPPORTED` |
| ST-05 | `sparktape_sell_shock_replenishment_prereg_v1.json` | `sparktape_sell_shock_replenishment_v1_closure.json` | `CLOSED_ESTIMATION_COMPLETE_WITH_INACTIVE_CHANGED_DIAGNOSTIC` |
| ST-07 | `sparktape_activity_stasis_prereg_v1.json` | `sparktape_activity_stasis_v1_closure.json` | `CLOSED_ESTIMATION_COMPLETE` |
| Dormancy Hazard v1 | `sparktape_dormancy_hazard_prereg_v1.json` | none | Not closed. See section 6. |

## 4. Frozen baselines and closed studies — do not reopen

Do not design Strategy C v4. The v3 closure says the newborn-long family is `CLOSED` and that another newborn-long entry needs genuinely new external evidence of a new market mechanism. Do not open the V1 holdout. Every closure that mentions it records `v1_holdout: UNOPENED` or `holdout_used: False`. No file named holdout was found. Do not mine a closed cohort for a replacement hypothesis. The closures explicitly set `production_fence_activated: False`, `replication_started: False`, and `historical_replay: False`.

| Study | Stored result that must stay closed | Why it is not a trading rule |
|---|---|---|
| Strategy C v1 | `CLOSED_UNSUPPORTED`. Reason: `NEGATIVE_ACROSS_ALL_PREREGISTERED_LONG_HORIZONS`. Development summary, not the holdout: 326 development rows, 302 returns, mean −0.0694, median −0.0300, win rate 0.109, catastrophic-loss rate 0.106. Population field on the preregistration: 466. | Holdout was not used. `strategy_c_buys: 0`. `reserve_change` is `NOT_ELIGIBLE_FOR_CANDIDATE_RULE_INTERPRETATION`. |
| Strategy C v2 washout/reclaim | `CLOSED_OPERATIONALLY_TOO_SPARSE`. 690 unique launches, 3 full signals, 0 executable entries, 0 completed round trips. Minimum was 30. | Not a P&L result. Thresholds were not loosened. |
| Strategy C v3 momentum restart | `CLOSED_OPERATIONALLY_TOO_SPARSE`. 948 unique launches, 18 structural full signals, 0 completed round trips. Maximum possible completed entries even under the generous bound: 15, still below 30. | Execution-gate audit left `EXECUTION_GATE_AUDIT_INCONCLUSIVE`. `v3_1_created: False`. `v4_created: False`. |
| ST-01 distribution risk | Spearman rho +0.071, two-sided p 0.333, n 188. Hypothesized direction was negative. | `NO_EVIDENCE_OF_ASSOCIATION`. Exposure was 1 on 122/188 rows. Metric is observed Pump-trade attribution, not wallet holdings. `v1_holdout: UNOPENED`. |
| ST-02 replacement demand | rho −0.214, p 0.000327, n 278. Preregistered direction was positive. | Opposite direction is explicitly `NOT_VALIDATED` and not a fence. 243/278 exposure values were 0. |
| ST-03 buyer renewal | rho −0.427, p 4.08e-16, n 332. Preregistered direction was positive. | Same ruling. 275/332 exposure values were 0. Retention was exactly 1 on 224/332. Closure warns of an activity-stasis confound and forbids a reversed hypothesis. |
| Risk Fence v1 | 1,208 launches, exposure common (784 true / 399 false), but only 67 primary-eligible (55 vs 12). 861 primary-gap-censored. | Single-socket censoring destroyed the sample. No p-value was calculated. Not a failed economic test. |
| Risk Fence v2 | 512 admitted. Primary-eligible 376 true vs 55 false. Both median retentions 1. Mann-Whitney p about 0.603. Hodges-Lehmann shift 0. | Hypothesis not supported. Eligibility rates differ (0.957 vs 0.462) because of quote composition. The analysis says not to adjust post hoc and not to mine slot variables. |
| ST-05 sell-shock replenishment | Estimation only. Taxonomy-eligible 141. Response-inactive 96/141. Active replenishment share 11/41 = 0.268, Wilson 95% about [0.157, 0.419]. | Not an alpha test. No hypothesis test, no threshold search, no future-outcome analysis. |
| ST-07 activity stasis | Estimation only. Taxonomy-eligible 595. Exact-stable 430/595 = 72.27%. Of those, inactive 429/430. Active-changed reserve-halved 98/165. | Not a hypothesis test. No production rule. |

Control hashes that closures say were not changed:

- Control A, repeated: `485e604389d4c04d9785600d8e48b4095fbb225bf407b82927ea8c3d58091292` — RECORDED HASH ONLY. The file was not isolated.
- Control B, previously observed: `cf7d2065aa644c97ebcb1118bbd2d7657b54d6de5f19bafdf4a37029b3b246f0` — RECORDED HASH ONLY.

`birth_research.py` says Control B is frozen. Do not edit it to make a new baseline.

Dormancy sessions that must not be quietly merged:

| Session | Stored ruling |
|---|---|
| `dh1-20261016-202016` | `SESSION_NOT_ADMISSIBLE`. One unexplained missing finalized Pump event at slot 457768264. Contributes 0 launches. Cox was not run. |
| `dh1-20261022-045654` | `UNPLANNED_EXTRA_PROSPECTIVE_SESSION_QUARANTINED`. Deploy doc says it contributes 0. Outcomes must not be inspected without an explicit protocol ruling. The runner rejects this session id. |
| `dh1-20261020-102656` | Admitted for integrity (`DH_REPLACEMENT_ADMISSION_INTEGRITY_VERIFIED`, completeness `PASS`, sigcache 6396/6396). Manifest still says `admitted_launches: 0` and `launch_accounting: SEALED_UNTIL_SAMPLE_GATE`. Cox was not calculated. |
| `dh1-20261022-041357` | `AUTHORIZED_NEXT_PROSPECTIVE_SESSION`, status `COLLECTED_RAW`. This is the only session the deploy doc tells an operator to restore. |

## 5. Counts, with the file that holds them

These numbers were read from the JSON named in the last column. They were not recomputed from raw tapes.

| Dataset | Count stored | File |
|---|---|---|
| Strategy C v1 population / development rows / development returns | 466 / 326 / 302 | `strategy_c_prereg_v1.json`, `strategy_c_prereg_v1_dev_baseline_summary.json` |
| Strategy C v1 development mean / median / win / catastrophic | −0.06940 / −0.02996 / 0.1093 / 0.1060 | same baseline summary. Holdout accessed: 0. |
| Strategy C v2 unique launches / full signals / round trips | 690 / 3 / 0 | `strategy_c_prereg_v2_closure.json` |
| Strategy C v2 milestone 300 unique launches | 362, frozen, not trimmed to 300 | `strategy_c_v2_prospective_300.json` |
| Strategy C v3 unique launches / structural signals / round trips | 948 / 18 / 0 | `strategy_c_prereg_v3_closure.json` |
| ST-01 admitted / primary eligible | 658 / 188 | `sparktape_distribution_risk_v1_closure.json` |
| ST-02 prospective launches / primary eligible | 1105 / 278 | `sparktape_replacement_demand_v1_closure.json` |
| ST-03 prospective / primary / live-complete / reconstructed-complete | 510 / 332 / 129 / 381 | `sparktape_buyer_renewal_v1_primary_analysis.json` |
| Risk Fence v1 launches / primary eligible / gap-censored | 1208 / 67 / 861 | `sparktape_risk_fence_v1_closure.json` |
| Risk Fence v2 admitted / primary true / primary false | 512 / 376 / 55 | `sparktape_risk_fence_v2_closure.json` |
| ST-05 taxonomy eligible | 141 | `sparktape_sell_shock_replenishment_v1_closure.json` |
| ST-07 taxonomy eligible | 595 | `sparktape_activity_stasis_v1_closure.json` |
| Dual-feed events A / B / both / A-only / B-only | 53455 / 28880 / 28481 / 24974 / 399 | `validation_summary.json` |
| Gap session sample launches | 406 | both gap validation JSON files |
| Dormancy prior admitted launches, before the two 2026-10-22 raw sessions | 346 | `sparktape_dormancy_hazard_v1_collection_deviation_20261022.json` |
| Dormancy manifest admitted launches | 0, sealed | `sparktape_dormancy_hazard_v1_prospective_manifest.json` |
| Early paper book | 1 open, 53 closed | `control_v1_paper.json` |
| `chain_raw.jsonl` | 124 lines | counted in this handover, file is small |
| Development baseline jsonl | 326 lines each | `strategy_c_prereg_v1_dev_baseline.jsonl` and `..._dev_secondary_baselines.jsonl` |

The 346 dormancy figure and the sealed 0 are both stored. They are not a finished sample. This handover did not open dormancy rows to reconcile them.

## 6. Tests, stored results, limitations, unresolved problems

**Tests.** About 40 `tests/test_*.py` modules are present, plus three Pump instruction fixtures. Matching `__pycache__` files exist for many of them under CPython 3.10. That only shows the files were imported sometime. No pytest report, JUnit file, or saved test log was found. **Tests were not rerun. Do not treat the bytecode as a pass.**

**Hash checks that were done.** All 17 `data/*.sha256` sidecars match the adjacent file bytes. Closure citations for the ST milestone, primary-analysis, estimation, v2 milestone, v3 milestone, and v3 execution-gate files were checked against those same sidecar hashes or by hashing the cited file. 14 cited analysis/milestone hashes matched the files. The preregistration hashes printed in the closures match the sidecar contents for every preregistration that has a sidecar.

**Stored scientific results.** Section 4 is the result list. None of those studies produced a production fence.

**Stored engineering results.**

- First gap reconstruction (`gap_reconstruction_validation.json`): `BLOCK_BACKFILL_VALIDATED: NO`. r60 matched 405/406, r300 matched 404/406, lifecycle 406/406, exposure 7/7. `getBlock` had to be rerun with `maxSupportedTransactionVersion` 1 because version 0 rejected produced blocks. RPC B saw 35.23% of the masked reference events. HTTP recovery of identities was recorded as 100% on the requested blocks, but the block-backfill verdict was still NO.
- Later canonical chain-order check (`canonical_backfill_validation.json`): `CANONICAL_BACKFILL_VALIDATED: YES`. 650/650 masked events recovered, 0 missing, 0 extra, 0 field mismatches, r60 and r300 406/406, 476/476 transaction indexes resolved. It also records 40 receipt-versus-chain reserve disagreements and `prior_block_backfill_validated: NO`. Those two verdicts are both supposed to remain. The YES does not erase the NO.
- Dual feed: 0 disconnects on both sockets, one dual gap of 0.097 seconds, 0 slots backfilled. Old single-socket complete windows 197/200. Dual-live complete 200/200. This is a ten-minute engineering check, not a robustness proof.

**Limitations that are written down.**

- Public Solana RPC is the default. It is not a dedicated feed. `canonical_validation.py` treats HTTP 429 as a retry.
- Provider A in the stored dual-feed summary is Solana Foundation `api.mainnet-beta.solana.com`. Provider B is PublicNode `solana-rpc.publicnode.com`. `collect_dual_validation.py` also contains an OnFinality public WebSocket URL. That URL was not the pair used in the stored 601-second summary.
- Pump logs are `logsSubscribe` at commitment `confirmed`.
- Native SOL on the bonding curve is often `Pubkey::default()`, while the execution allowlist spells SOL as wrapped SOL, null, or empty. The V3 audit left 6 signals unresolved for that reason and 3 as genuine non-SOL. Confirmed false rejections: 0. No correction was implemented.
- Distribution-risk and buyer labels are observed Pump trade addresses. They do not see Token or Token-2022 transfers.
- ST-02 and ST-03 exposures are mostly zeros. A significant Spearman in the wrong direction is not a rule.
- Risk Fence v2 groups are badly imbalanced. The file says not to post-hoc adjust.
- ST-05 has 4 `INACTIVE_CHANGED` rows. The closure says they are a platform diagnostic and must not change the frozen estimand.
- Dormancy Hazard is the unfinished study. Cox has not been run. The sample gate has not been evaluated. One admissible session is sealed. One later raw session is authorized but not finalized. One extra session is quarantined. One earlier session failed completeness.
- `curve_quote.py` says it is not validated for paper P&L.
- Era A paper (`control_v1_paper.json`) was not connected, in these files, to the Strategy C closures.

## 7. Solana feeds, RPC, and recorded infrastructure changes

Hardcoded or default endpoints, all public:

| Use | Endpoint |
|---|---|
| DexScreener | `https://api.dexscreener.com` |
| GoPlus | `https://api.gopluslabs.io` |
| GeckoTerminal | `https://api.geckoterminal.com/api/v2` |
| Pump frontend metadata | `https://frontend-api-v3.pump.fun/coins` |
| RPC/WS A default | `https://api.mainnet-beta.solana.com`, `wss://api.mainnet-beta.solana.com` |
| RPC/WS B default | `https://solana-rpc.publicnode.com`, `wss://solana-rpc.publicnode.com` |
| Extra public WS in the dual-validation collector | `wss://solana.api.onfinality.io/public-ws` and HTTP `https://solana.api.onfinality.io/public` |
| Overrides | `SOLANA_WS_URL_A`, `SOLANA_HTTP_URL_A`, `SOLANA_WS_URL_B`, `SOLANA_HTTP_URL_B` |

Recorded changes, from the validation JSON and code comments:

- `getBlock` must send `maxSupportedTransactionVersion: 1`. Version 0 rejected produced blocks during the gap session.
- Canonical outcome order replaced websocket arrival order for historical state. Receipt time is still kept as live availability and must not be overwritten.
- Single-socket continuity was abandoned as a scientific censor after Risk Fence v1. Dual sockets plus explicit gap censoring replaced it. Backfill does not make a window live-complete.
- Index scope is the chain-frontier slot of each horizon. An earlier slot cannot outrank a later slot.
- Non-finalized signatures are excluded. The canonical file records 1 such exclusion.
- Dormancy code was corrected so events strictly after birth+900 are outside the scientific window. The implementation note says required slots stayed 5363 on the excluded session, 946 post-900 slots were dropped from the requirement, raw tapes were not rewritten, and no scientific result was viewed before that correction.
- IDL pin is `pump-idl-2026-10-02`, taken from the public Pump docs IDL. Schema string is in `pump_decode.py`.

There is no evidence here of a paid RPC vendor, Geyser, or Yellowstone stream.

## 8. Modules that could help a later arbitrage or launch study

These are capabilities, not permission to reuse a closed P&L. Copy the code. Do not copy a closed cohort into a new hypothesis.

| Need | Module | What it actually does |
|---|---|---|
| Token launch detection | `pump_decode.py`, `collector.py`, `chain_live.py`, `birth_research.py` | CreateEvent decode and prospective birth intake. |
| Pool / curve state | `idl/pump.json`, `birth_research.py` reserve notes | Real versus virtual SOL reserves on the Pump bonding curve. Not an AMM pool outside Pump. |
| Migration off the curve | lifecycle flags inside the risk-fence and strategy closures | `MIGRATED_BEFORE_EXIT`. Strategy C v3 says PumpSwap is not used. This tree does not contain a PumpSwap execution model. |
| Executable size | `curve_quote.py`, `outcome_v1.py`, `v2_path.py`, `v3_path.py` | Paper curve quotes and `pre_migration_pump_execution_return`. Notional used in the frozen protocols is 50,000,000 lamports (0.05 SOL). Stops were none. |
| Quote asset | `quote_normalization.py`, `execution_gate_semantics.py` | Derived metadata only. Does not rewrite raw evidence. Documents the default-pubkey versus wSOL allowlist mismatch. |
| Liquidity continuity | `coverage.py`, `dual_coverage.py`, `gap_reconstruction.py`, `canonical_state.py` | When a printed reserve is missing because the socket dropped, versus when the curve actually changed. |
| Shock then refill | `st05_sell_shock.py` | Measurement of sell shock and later replenishment. Estimation closed. Not a signal. |

`quote_normalization.py` is marked unused by Strategy C v2 and v3. `execution_gate_semantics.py` is marked not imported by the collector or by `v3_path.py`.

## 9. Overlap with SOLARB-PREDATOR, AlphaRadar, or Solana Arb

No source, note, or result for SOLARB-PREDATOR, AlphaRadar, or Solana Arb is in this workspace. Nothing below describes those codebases. It only says which SparkTape pieces sit on the same problems those names suggest.

| Likely shared problem | SparkTape piece | Do not treat as |
|---|---|---|
| New token / launch detection | CreateEvent intake, `collector.py` | A sniper. Closed Strategy C says the newborn long did not survive its own tests. |
| Pool creation and liquidity migration | Bonding-curve reserves and migration censoring | A multi-venue arb graph. PumpSwap is explicitly unused in v3. |
| Executable liquidity | Curve quote and pre-migration execution return | A certified fill model. `curve_quote.py` says it is not validated for paper P&L. The V3 execution gate is inconclusive. |
| Two RPC views of one chain | `dual_coverage.py` | Production redundancy. One ten-minute public-RPC check. |

Crowdtape is named in the SparkTape README as a sister desk (Hyperliquid crowding). Crowdtape files exist elsewhere under `/workspace/artifacts/projects/`. They are not part of this handover and were not reviewed for it.

## 10. Smallest package that can verify the claims

Copy these. They are enough to re-read every closed classification and to check the hashes above. They are not enough to recompute a cohort from raw logs.

1. Every `data/*closure.json`, `data/*prereg*.json`, and the 17 `data/*.sha256` sidecars.
2. The milestone, primary-analysis, and estimation JSON files named inside those closures.
3. `data/strategy_c_v3_execution_gate_audit.json`.
4. `data/dual_feed_engineering/*.json` (four files).
5. `data/sparktape_dormancy_hazard_v1_collection_deviation_20261022.json`, `..._implementation_note.json`, `..._session_exclusion_dh1-20261016-202016.json`, `..._prospective_manifest.json`.
6. `README.md`, `requirements.txt`, `deploy/SPARKTAPE_RUNNER_DEPLOY.md`, `deploy/runner_bundle_file_hashes.json`.
7. If TRANSFORMER needs to interpret semantics rather than only trust the JSON: the `.py` modules and `idl/pump.json`. Exclude `__pycache__`.

Do not put `data/session_archives/` in the small package. Those chunks are the raw tapes behind the session hashes. Export one session only when a hash in the JSON has to be re-checked, and do not unpack `dh1-20261022-045654` to inspect outcomes.

Do not export `control_v1_paper.json` as scientific evidence. It is an earlier paper book and was not tied to the closures.

The file list, with export class, is in `TRANSFORMER-SPARKTAPE-EVIDENCE-MANIFEST.md` next to this handover.

## What TRANSFORMER may and may not do with this

May: read the closed JSON, reuse decoders and coverage code on new data, cite the stored negative and sparse results so the same newborn-long question is not asked again.

May not: reopen Strategy C, ST-01, ST-02, ST-03, either Risk Fence, ST-05, or ST-07; open the V1 holdout; score the quarantined dormancy session; treat an opposite-direction Spearman as a fence; change a frozen threshold; or describe any of this as a live trading result.

Dormancy Hazard v1 is the only study that the files themselves still leave open, and even that one is locked to its existing preregistration, its sealed accounting, and its quarantine rules.
