# E011-A2 UID / DAC preflight — 2026-11-03
Status: **PASS_LIMITED**, not an independent E011-A2 PASS.

## Executed synthetic test
A Linux/root orchestration harness dropped privileges via `setpriv` to role UIDs R1=31001, R2=31002, R3=31003. Each role had its own `0700` directory and child process. R1 read its dev file and generated a deterministic UTF-8-uppercase candidate. Candidate SHA-256 was frozen before the R2 held-out file was created, then transferred in exact bytes. R2 executed the frozen candidate, froze output SHA-256, and transferred only output to R3. R3 received a private expected-answer key and returned synthetic PASS.

Observed: **6 DENY** read probes (including R1 symlink to R2 stimulus), **4 ALLOW** reads, three distinct role UIDs, separate child PIDs, frozen candidate/output transfer hashes matching, and correct synthetic verdict. The executable and a detailed JSON log were generated locally in the Run 009 deliverable bundle. No existing E004–E006 held-out stimulus or evaluator keys were opened.

## Limitations / next action
The host filesystem and privileged orchestrator were shared. No separate secure model contexts, mount/network namespace isolation, full exposure accounting, independent review or comparable isolation overhead. This proves limited Linux DAC semantics, not full model/runtime isolation or safe held-out evaluation. **E011-A2 PARTIAL; E011-B BLOCKED; E004–E006 BLOCKED.** Next action: reproduce across independent model contexts/workspaces and record a precommitted signed artifact/exposure/overhead receipt. Do not count this as E011 full completion.
