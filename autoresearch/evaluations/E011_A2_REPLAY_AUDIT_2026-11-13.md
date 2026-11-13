# E011-A2-R historical-source replay receipt — 2026-11-13
**Status: REPLAY_PASS_LIMITED. Not E011-A2 PASS.**

Source artifacts: `AutoResearch_Run_009T_2026-11-07.zip` SHA256 `1fa78c6956c4ce1d03016d56d9a6099bafbba459258ddd861142e85419a9ebba`; `AutoResearch_Run_009U_2026-11-10.zip` SHA256 `b462a1299e441b31d235540598eb3e2bc90e1d8af4facfee447c4c9b81ee11b4`. Hashes anchored retrospectively for this audit, not prior runs.

Independent fresh Python process invoked both prior unittest suites: Run 009T 14/14 PASS; Run 009U 10/10 PASS. Run 009T's previous UID receipt classified NOT_READY and returned expected exit 1. Run 009U witness returned TRACE_CONSISTENT_NOT_ISOLATION_PROOF and releases_E011_B=false. Deliberately changed archive bytes caused checksum mismatch and rejection.

Exact GitHub executable paths `autoresearch/experiments/e011_a2_admission_gate.py` and `autoresearch/experiments/e011_witness.py` yielded 404 on this review branch; narrative receipts still available. Does not establish absence of all alternate code locations. Audit script, original ZIPs, raw structured JSON, SHA manifest and full report are in the locally delivered Run 009V bundle; they are not represented as committed GitHub binaries.

Limitations: two convenience cases, earlier user-delivered bundles not independently authenticated, not a prospectively registered evaluation, no independent R4 reviewer, no model-context isolation or E004–E006 test reads. E011-A2 **PARTIAL**, B **BLOCKED**, E004–E006 valid results **0**. No automatic promotion.
