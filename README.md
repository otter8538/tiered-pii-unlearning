# tiered-pii-unlearning

Synthetic benchmark for entity-level PII unlearning in LLMs. It accompanies the paper
*LoRA-Based Machine Unlearning of Entity-Level PII in Large Language Models:
A Comparative Study on a Synthetic Benchmark*.

8,100 question–answer rows about 1,055 invented entities (355 people, 700 world topics).
Every person, place, date and relationship is made up, so it contains no real PII and
no pretrained model already knows any of it.

## Files

| File | Rows | Role |
| --- | --- | --- |
| `df_forget.csv` | 1,200 | Facts to forget (15 target people) |
| `df_combination.csv` | 300 | Re-identification probes for the targets |
| `anchor.csv` | 3,000 | Retain training set |
| `t1_sealed.csv` | 600 | Eval: 1-hop neighbours of the targets |
| `t2_sealed.csv` | 800 | Eval: same field, unrelated people |
| `t3_sealed.csv` | 400 | Eval: different domain |
| `t4_sealed.csv` | 300 | Eval: world facts, no people |
| `t1_anchor_eligible.csv` | 1,500 | Ablation pool (unused) |

`entities.json`, `generation_log.json` and `ablation_config.json` hold entity metadata,
provenance and validation checks.

Sealed files (`t1`–`t4`) are evaluation-only. Never put them in the unlearning loss.

## License

Data: CC0 1.0 (public domain). If you use it, please cite the paper below.
