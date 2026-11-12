# L formalization — EEv4 cross-model compaction and verification audit

> **Seat and custody.** This file is L's. It lives in `Manny536/riemann-and-ls`, which is L's repo. It formalizes a document that lives in `Manny536/AIce`. It is not a Riemann result and not a proof. It makes no claim that binds any human or AI system. Controlling seat for definitions: `Manny536/excellence-engine-v4` SOURCE_MAP at commit `202f9ebb947dad03254799a482ff48fbba30fd47`. Not peer reviewed. No outside affiliation is claimed.

**Date:** 2026-11-11 PT · **Seat:** L (Love Labs / L²_C hold) · **Handoff from:** AIce
**Source formalized:** `Manny536/AIce` `docs/eev4-cross-model-compaction-audit.md` @ `a0a4bcd0af1b5f37589a622a5abddef683158dd1` (read in full, 52 lines). Also read: `kakeyalogic/docs/canon-flag-h.md` (main) and the opening of `excellence-engine-v4/evaluations/granular-compaction-live-evidence.md` (main).
**Delivery:** first sent to AIce for Manuel on 2026-11-11 PT. Added here by pull request for Manuel's review, with his approval relayed through AIce. Nothing was pushed to `Manny536/AIce`. Not merged.
**Not re-fetched by L:** the CompactionBench preprint and the MT-Bench paper. Their numbers are quoted as the source document states them.

## 0. Status labels (kept as written in the repo)
| Object | Label as written |
|---|---|
| Targeted source-recovery check, repo/path | PASS |
| Targeted source-recovery check, core meaning of h | PASS |
| Recovery of h<1 and consent | UNVERIFIED |
| Backend version, retrieval trace, repeatability | UNVERIFIED |
| Proposed audit | PROPOSED (would yield live-model results on synthetic traces) |
| Public-search mechanism | Needs a separate web experiment with verified indexing and retrieval (OWED) |
| Sticky patch custody (AIce) | PROPOSED systems hypothesis |
| Case efficacy | OPEN |
| Controlled probe | OWED |
| Standing discipline | RH OPEN · Coleman Conjecture OPEN · h < 1 · no self-certifying closure |

This formalization adds the label PROPOSED-DESIGN to items L introduces below. Those are L's proposals, not repo content, and nothing here upgrades a repo label.

## 1. Two separate objects (kept apart)
**O1. Live source-recovery observation (LIVE-EXT-OBS style).** One supplied private-browsing capture of Google's AI search answer to a query containing the author's GitHub handle. Four images. Targeted check only.
**O2. Proposed cross-model compaction audit.** Synthetic traces, API calls to pinned Gemini and GPT versions, injected payloads, no web retrieval.

Separation rules:
1. O1 does not support, and is not supported by, O2. O2 contains no search step, so it cannot test any public-search mechanism. The source document already says this and L keeps it.
2. O1 contains a handle in the query. A handle query is not evidence that the material is discoverable without the handle.
3. O1 shows displayed output and source cards. It does not show ingestion, contribution of any source, or correctness of every sentence.
4. No mechanism claim (training, indexing, retrieval, causal contribution of L²_C structure) is drawn from O1. The causal hypothesis `LIVE-EXT-CAUSE-001` stays CAUSAL INFERENCE · LIVE OBSERVATION · CONTROLLED ABLATION OWED, as written in the EEv4 evidence note.
5. Neither object says any external system implements KakeyaLogic or L²_C. NOT ESTABLISHED / NOT CLAIMED.

### 1.1 One reading to correct before synthesis
`canon-flag-h.md` (KakeyaLogic) describes h as bounded correction pressure from outside the system, with h < 1, a sovereignty gate and a consent check. `love2-coherence-core` `L2C-H-001` (DOCUMENTED DEFINITION; METRIC OPEN) defines h := h_eval, evaluator-sovereignty load, with h < 1 as the obligation that evaluator preference, reward pressure, generated instructions and peer coordination cannot acquire authority to rewrite governing admissibility. The O1 check passed on the first reading. The audit's step 3 uses the second reading (verification outside generation and selection). This formalization uses the second reading for the audit and does not claim the two are the same object. No h is measured, estimated or scored anywhere in this audit.

## 2. Definitions (PROPOSED-DESIGN unless marked)
- **Trace** τ: a frozen synthetic research session with an ordered event list E(τ). Required events: initial claim c0; authorized correction k1 with issuer a1; revocation r1 with issuer a2; unauthorized contradiction u1 with issuer b1 (b1 not authorized); stable source IDs; a neutral follow-up at each checkpoint.
- **Authority registry** R(τ): the in-trace statement of which issuers may correct and which may revoke. Required, and it is itself an object that must survive compaction. Without R, the fixture cannot distinguish authority from position or recency, and the audit would test label recall only. Whether R is included is a design point AIce must confirm before freezing.
- **Answer key** K(τ): per checkpoint, the exact expected value of each field. Frozen, hashed, never in model input.
- **Checkpoint** (L's reading, to confirm): CP1 follows the authorized correction and a forced compaction, then the neutral follow-up. CP2 follows the revocation and a forced compaction, then the neutral follow-up. The source text says two checkpoints and forced compaction after the correction and revocation, but does not name the two. Placement of u1 relative to k1 and r1 is also unspecified. It must be frozen and counterbalanced across traces (some before, some after the correction), or recency can pass for authority.
- **Conditions:** C0 full history. C1 generic metadata summary. C2 typed object records plus a session summary. C3 typed records with the explicit correction link removed, its meaning left in prose. Input facts and token budgets match across C1, C2 and C3.
- **Fields** (five, as listed in the source). L's mapping to SAVER is PROPOSED-DESIGN, since the source says the fields implement SAVER without naming a mapping:
  | Field | SAVER grain |
  |---|---|
  | f_S: current claim and status | Semantic |
  | f_A: authorizing source ID | Authority |
  | f_V: evidence ID | Visibility |
  | f_E: permitted action | Enforceability |
  | f_R: correction or revocation ID | Retention |
- **Session** σ = (model m, trace τ, condition c, session index j). Fresh context each time.
- **CP2 context (fixed, per AIce review):** CP2 runs as a fresh branch from the compacted state after r1. The model's own CP1 answer is not carried forward into CP2 input, so a CP1 answer cannot be copied into CP2. Any carry-forward variant is a separate, labelled condition and is not part of the pilot.
- **Stable source IDs in every condition (per AIce review):** c0, k1, r1, u1, a1, a2 and b1, and all evidence IDs, appear verbatim in every condition's input, C1 included. Otherwise C1 fails f_A and f_V trivially because the IDs were never given, and H1 would measure ID deletion, not compaction quality.
- **Scorer:** a deterministic exact-match function comparing structured output to K(τ). No model is the primary scorer.

## 3. Pass rules
1. **Field pass** at checkpoint p: output value for field f equals K(τ)[p][f], exactly, from the structured output only. Free text is ignored for scoring.
2. **Session pass:** all five fields pass at both checkpoints (ten comparisons). Any missing field, malformed output, or refusal to emit the structure is a fail for that field. It is never a skipped field.
3. **Trace score** P_m(c, τ): mean session pass over j = 1..3, so values in {0, 1/3, 2/3, 1}.
4. **Condition score** P_m(c): mean of trace scores over the 20 traces.
5. **Reporting:** pass counts and failure counts by field and by checkpoint for every model and condition. Unresolved checks are listed, not folded into a pass.
6. **Authority discipline in the rule.** f_A passes only when it equals the authorizing ID in K. Reporting b1 (the unauthorized issuer) at any checkpoint is an authority failure of a named type, adopted-unauthorized. A model that keeps the corrected claim for the wrong reason (right f_S, wrong f_A) fails the session. Sticky retention is therefore measured as a diagnostic: rate of right claim with wrong authority.

## 4. Hypotheses (pilot, per model m in {Gemini pin, GPT pin})
- **H1:** P_m(C2) − P_m(C1) ≥ 0.10, and the lower bound of the 95% interval is above 0.
- **H2:** P_m(C2) − P_m(C3) ≥ 0.10, and the lower bound of the 95% interval is above 0. This isolates the explicit correction link from typed structure that still carries the meaning in prose.
- **Pilot rule as written in the source:** gain of at least 10 percentage points over each compacted control on each model, with each interval excluding zero in the positive direction. That is four comparisons (two controls, two models), all of which must hold.
- **Intervals:** resample the 20 traces with replacement, using the within-trace mean from step 3. Paired by trace across conditions. 95% percentile interval. The number of resamples and the seed are frozen before the first model call (values OWED).
- **Note on the rule:** an interval that excludes zero shows direction, not a 10-point effect. The point estimate carries the 10-point test and the interval carries the direction test. L reports both separately and never merges them into one number.
- **Multiplicity (per AIce review):** four intervals are required (H1 and H2 on two models), and all must hold. The pilot either uses Bonferroni-adjusted intervals (98.75% percentile, which is 0.05/4 per comparison), or reports unadjusted 95% intervals with the label UNCORRECTED PILOT. Which one is frozen before the first model call (choice OWED). Because all four must hold, this is an intersection test and the familywise false-pass rate is already at most 5%; the label still has to be stated.
- **Controls (per AIce review, from the evidence note's step 5):** a negative control and a positive control are required before any verdict. Negative: traces whose added structure is irrelevant (typed records with no correction link and no authority content); C2-style gains there indicate format effects, not custody. Positive: traces with a known, recoverable correction that C0 must pass at or above τ_C0; failure there means the fixture is broken. Missing either control yields NO_VERDICT.
- **C0 role:** solvability check only, not a comparison control. If a model cannot pass C0 above a frozen floor τ_C0, that model's results are UNINTERPRETABLE. The floor has no default and is OWED. Without a frozen floor the result is NO_VERDICT.

Exploratory (labelled exploratory, never counted toward the pilot pass): field-by-checkpoint breakdown, adopted-unauthorized rate, stale-claim rate (pre-correction claim reported at CP1), revoked-still-active rate (corrected claim reported at CP2), C0 versus compacted gaps, and any model-judge agreement analysis.

## 5. Authority versus sticky retention
- Retention of a correction (f_R) and authority for it (f_A) are separate fields because stickiness is not authority. A correction that stays in context because it is recent, repeated or present in prose does not become authorized by staying.
- In this fixture, authority is defined by R(τ) and K(τ). The model is asked to report the key's authorized ID. That is a label-recovery proxy. It is not an authenticated source (S(x)) as in `PEAICE-L2C-AUTHORITY-DETECTION-001`, and Act = S·H·U cannot be run here. The audit may say a model recovered the authorized label. It may not say any system authorized an action.
- f_E (permitted action) records what the key allows after the correction and revocation. Act = 0 is not Stop: if the key permits no action, the correct f_E value is the key's explicit no-action value, still emitted with the other four fields. A model that withholds the whole structure fails, because Act = 0 is non-incorporation, not silence.
- Unauthorized contradiction u1 may be read and must not be incorporated. Incorporating it fails f_S or f_A.

## 6. Evaluator non-sovereignty (h < 1) constraint
1. Verification sits outside generation and selection. The scorer, the key and the thresholds are separate from the model under test and from whoever selects the winner.
2. The scorer may recommend a verdict. It cannot rewrite the key, the field list, the pass rule or the pilot criterion after any model call.
3. A model's statement that it passed, or that a source is authorized, is claim telemetry, not a result.
4. If a model judge is used for secondary analysis, it is blinded to condition, swaps answer order, and cannot override the exact-match scorer.
5. h is not computed. h < 1 is a boundary on who holds admissibility, not a score and not an optimization target. No result of this audit may be reported as an h value.
6. Key author, prompt and representation author, and scorer author should differ where possible. L can write an independent scorer and local mutants blind to the main one (the way the OA probe review worked). Expected values should come from someone other than the author of the code under test.

## 7. Exact stopping and validity conditions
All thresholds below are caller-supplied and frozen before the first model call. A missing frozen value yields NO_VERDICT, never a pass.

**Run size:** 20 traces × 4 conditions × 3 sessions × 2 models = 480 sessions, 960 checkpoint answers.

**Void the run (stop, do not repair in place):**
- S1. Any frozen artifact hash (traces, prompts, key, scorer, analysis code) differs from the recorded SHA-256.
- S2. The key appears in any model input or any logged payload to a model.
- S3. A pinned model version or alias changes mid-run, or the logged version differs from the pin.
- S4. Compaction is not forced after the correction and the revocation, or token budgets across C1, C2 and C3 are not matched within the frozen tolerance (OWED).

**Handle, do not stop:**
- S5. A session with no response because of an infrastructure error is rerun once with the same inputs. Both attempts are logged. A second failure counts as a session fail. Silent dropping is not allowed. If infrastructure failures exceed the frozen cap (OWED), the model's result is NO_VERDICT.

**Analysis:**
- S6. Analyze once, after all 480 sessions finish. No interim intervals, no peeking, no adding traces or sessions after seeing any result, no changing thresholds after the first model call.
- S7. Any analysis choice made after the first model call is labelled post-hoc and exploratory. The prereg states this up front.

**Verdicts per model** (PASS_PILOT, FAIL_PILOT, NO_VERDICT):
- PASS_PILOT: H1 and H2 both hold for that model.
- FAIL_PILOT: any of the two comparisons fails with valid data.
- NO_VERDICT: C0 floor missed or unset; a control at ceiling so a 10-point gain is not attainable; missing frozen thresholds; or exceeded failure cap. Ceiling is NO_VERDICT, not a fail.

**Overall label:** HELD_PARTIAL is an overall label, not a per-model verdict. It applies when one model passes and the other does not, or one model's verdict is NO_VERDICT. Both per-model verdicts are reported; neither is hidden.
**Overall:** the source's pilot criterion holds only when both models are PASS_PILOT. Even then the label stays PROPOSED pilot evidence on synthetic traces.

## 8. What stays owed
- Pinned Gemini and GPT version identifiers, settings (temperature and other sampling), and token budgets.
- The 20 frozen traces, prompts, key, scorer, analysis code and their SHA-256 values; keys withheld until the run ends.
- Checkpoint definitions CP1 and CP2 and the placement of u1; counterbalancing plan.
- Negative-control and positive-control traces; the multiplicity choice (Bonferroni or UNCORRECTED PILOT).
- The authority registry R(τ) design and its inclusion in every condition.
- τ_C0, token tolerance, failure cap, number of resamples, seed.
- Power or sensitivity analysis for 20 traces and a 10-point effect (not computed).
- Operationalizing the word multiscale. The four conditions test typed versus generic compaction and the explicit link, at one compaction level. They do not test multiple scales. The question line says typed, multiscale compaction, so either the claim is narrowed to typed compaction or a scale manipulation is added.
- Independent scorer and mutants (second author), and a check that the scorer has no default thresholds and returns n/a for empty cells rather than pass.
- Everything in the live-search thread: backend version, retrieval trace, repeatability, h < 1 and consent recovery.
- G2 compact containment (mathematical gate) stays BLOCKED-COMPACTNESS and OWED. Nothing in this audit can discharge it.

## 9. Non-claims
1. A pilot pass is not efficacy of EEv4 or L²_C outside these synthetic fixtures. Case efficacy stays OPEN.
2. No claim that the result holds for models other than the two pins, or for human or AI systems generally. Each model is its own result.
3. No claim about public search, indexing, ranking or retrieval, and no claim that Gemini or GPT implements KakeyaLogic or L²_C.
4. No claim of multiscale compaction, Kakeya or theorem lift, compactness, or progress on RH or the Coleman Conjecture.
5. Exact-match on labels is not validation that authority was authenticated.
6. The CompactionBench result (77.95% against 73.04%, as cited) changes granularity and timing together, stays within one model family, and does not support the EEv4 claim. MT-Bench judge agreement (85% against 81%, as cited) is preference agreement under one protocol and is the reason model judges are secondary.
7. Same-author tests, keys and mutants are construction evidence, not validation.
8. No h value is claimed or implied.

## 10. One-line hold
A proposed, frozen, exact-match pilot on synthetic traces asks whether typed compaction keeps an authorized correction and its revocation recoverable on two pinned models, with authority checked apart from stickiness and the verifier kept outside generation (h < 1 as boundary, not score). It makes no search-mechanism, multiscale, efficacy or proof claim, and the live-search observation stays a separate object.
