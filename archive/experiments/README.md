# Archived experiment configs

Configs for experiments that did not become a final submission. Nothing in `src/`, `scripts/`, `tests/` or the reproduction entry point (`python -m r2ai.reproduce`) reads them; they are kept as a record of what was tried. Files were moved here with `git mv`, so `git log --follow` shows their history.

They contain absolute input paths of the development machine (`D:/GitHub/...`) and the inputs they name are not part of the data package, so they do not run as-is.

Scores below are public-leaderboard Final scores under the passage-matching rule from 23 Oct (metric v2), compared with the configuration each variant was derived from.

| File | What it tested | Outcome |
|---|---|---|
| `configs/s40-abl-free-v2-noCmax.json` | ablation: drop C-max from the RRF fusion | −0.0024, C-max kept |
| `configs/s36-abl-p4b-v3-noCmax.json` | same ablation on the 120A pool | no score recorded |
| `configs/s36-abl-p4b-v3-noJina.json` | drop Jina from the 120A pool fusion | no score recorded |
| `configs/s40-d400-noJina.json` | deeper candidate pool (400 instead of 300) | −0.0074, pool 300 kept |
| `configs/s40-cut150.json` | cap output at 150 documents per question (refit calibration) | −0.0007; Doc F2 fell although the refit predicted about +0.04 |
| `configs/s40-cut130.json` | cap output at 130 documents per question (refit calibration) | −0.0071 |
| `configs/s41-cut90.json` | cap output at 90 documents per question | no score recorded |
| `configs/s41-d400-cut150lam.json` | pool 400 combined with the 150-document cap | no score recorded |
| `configs/s40-recal-noJina.json`, `configs/s40-recal2-noJina.json` | refit the probability calibration | not adopted; original calibration kept |
| `configs/s36-chunk-rule-fair.json` | early spec of the passage-carrier rule | superseded by the rule inside the final config |
| `configs/s36-s37-120A-free-v1.json` | earlier version of the 120A free-pool config | superseded by `-free-v2` |
| `configs/s36-s37-120A-p4b-v2.json` | earlier version of the 120A config | superseded by `-p4b-v3` |
| `configs/s36-s37-apply.json` | first generic apply config | superseded |
| `configs/submission-sub06.yaml` | first leaderboard submission (early index, about 124k documents, Final 0.063 under metric v1) | historical |

The configs used by the submitted files stay in `configs/`; `docs/THUYET_MINH.md` section 4.3 lists which config builds which submission.
