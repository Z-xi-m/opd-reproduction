# 01 - THUNLP OPD

Fork: https://github.com/Z-xi-m/OPD

Local source: `../01_thunlp_OPD`

## Target

Reproduce the main OPD workflow from the repository and identify the minimum
hardware and dependency setup needed for a reliable run.

## Entry Points

- `README.md`
- `on_policy_distillation.sh`
- `scripts/repro/minimal_opd_a1004.sh`
- `verl/examples/ppo_trainer/on_policy_distillation.sh`

## First Run Plan

Use `A100_4` for a smoke reproduction on the currently free A100 80GB GPUs. This is not intended
to reproduce the full paper table; it only verifies the OPD training loop:

- student on-policy rollout,
- teacher token-level log-prob reward,
- top-k reward construction,
- PPO-style student update,
- checkpoint and validation-log writing.

The run uses the repository's included DAPO-Math parquet and AIME24 validation
set. Model checkpoints are downloaded to `/data/zhu.ximo/opd_repro/models`.

```bash
cd /data/zhu.ximo/opd_repro/thunlp_opd
conda activate opd_verl
bash scripts/repro/minimal_opd_a1004.sh
```

Key smoke-test overrides:

| Setting | Value |
| --- | --- |
| GPUs | `CUDA_VISIBLE_DEVICES=1,2,3` by default; script derives GPU count automatically |
| Training steps | 5 |
| Train data | `datasets/dapo-math-17k.parquet` |
| Validation data | `datasets/test_data/AIME24/test.parquet` |
| Student | `lllyx/Qwen3-1.7B-SFT` |
| Teacher | `lllyx/Qwen3-4B-Base-GRPO` |
| OPD estimator | `token_reward_direct` |
| Top-k | `16` |
| Top-k strategy | `only_stu` |
| Reward weighting | `student_p` |

## Checklist

- [ ] Read repository README and scripts.
- [ ] Record environment requirements.
- [ ] Prepare datasets and model paths.
- [ ] Run a minimal smoke test.
- [ ] Run the selected reproduction experiment.
- [ ] Record results and deviations.

## Notes

TBD.
