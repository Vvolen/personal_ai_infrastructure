# E004-E006 Evaluation Precommit Manifest v1

Status: frozen before candidate development or evaluation
Frozen: 2026-08-14
Scope: E004, E005, E006

## Immutability rule

These v1 artifacts are append-only historical inputs once committed. Do not edit a v1 dataset after any baseline or candidate run begins. A correction requires a new version, new hashes, an exposure/contamination note, and a fresh baseline. Any hash mismatch invalidates cross-run comparison against this manifest.

The Git commit containing this manifest is the authoritative precommit receipt. The content hashes below make later drift independently detectable.

## Frozen artifacts

| Experiment | Artifact | Development IDs | Held-out IDs | SHA-256 |
|---|---|---|---|---|
| E004 | `E004_FRONTIER_SCAN_DATASET_V1.md` | E004-D01..D08 | E004-H01..H04 | `32b4183740580aab62997450eaed6f0fbfd0b7dfbf3b38a5d437996d45499368` |
| E005 | `E005_TRAJECTORY_ATTRIBUTION_DATASET_V1.md` | E005-D01..D06 | E005-H01..H04 | `1e1e64072ec0a0771d49a31761a49e9436effb6da34799c2069a136e0720ee4e` |
| E006 | `E006_RETRIEVAL_STOP_DATASET_V1.md` | E006-D01..D06 | E006-H01..H04 | `e84f180ff0778b1b915abe7ae5be2f1f2cc6b5d7c8006e7efba938afd53e8a8c` |

Frozen outer-governance reference:

- `../BIWEEKLY_AUTORESEARCH_GOVERNANCE_LOOP.md`
- SHA-256 at precommit: `752c69011b267e63bf25d6e1f244302f06f09328f2bf1065b785d0256d1f18b5`

## Split and exposure policy

1. Dataset stewards may inspect all artifacts to verify the precommit, but harness authors/evolvers may use only development cases while proposing or tuning candidates.
2. Freeze the candidate profile/version and expected causal mechanism before releasing held-out stimuli to the execution harness.
3. Do not pass evaluator-only expectations to either lane before its output and decision are recorded.
4. Log case IDs, actor/agent, timestamp, harness version, model snapshot, tool and environment hashes, and whether any prior exposure occurred.
5. A case exposed to candidate development is contaminated and cannot count as held out. Mark it contaminated; do not silently replace it. Create a new dataset version before claiming held-out evidence.
6. Run baseline and candidate against the same split and evaluation tuple. Preserve all failed, null, and negative results.
7. The public location of these files does not make them development data. Isolation is an execution-policy property: the candidate-development context must not receive held-out prompts or evaluator keys.

## Precommitted decisions

- E004 may tune on eight development tasks and promotes only on the four untouched held-out tasks using the experiment board's protected-quality gate.
- E005 may tune attribution instructions on six development fixtures; its four held-out fixtures test evaluator drift, security regression, process-invalid correctness, and a genuine isolated gain.
- E006 may tune the evidence-sufficiency threshold and weights on six development questions; its four held-out questions test repository delta, expertise-compounding evidence, a potentially unanswerable comparison, and conflicting evidence.
- No result from E004-E006 can activate D-AR-011 through D-AR-015 automatically. Promotion remains a separate recorded human-review decision under `STATE.md`'s doctrine status boundary.

## Verification command

From the repository root:

```bash
shasum -a 256 \
  autoresearch/evaluations/E004_FRONTIER_SCAN_DATASET_V1.md \
  autoresearch/evaluations/E005_TRAJECTORY_ATTRIBUTION_DATASET_V1.md \
  autoresearch/evaluations/E006_RETRIEVAL_STOP_DATASET_V1.md \
  autoresearch/BIWEEKLY_AUTORESEARCH_GOVERNANCE_LOOP.md
```

The output must match the four hashes recorded above before a comparable run starts.
