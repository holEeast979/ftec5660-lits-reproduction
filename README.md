# FTEC5660 LiTS reproducibility study

A small reproducible comparison of LiTS ReST-MCTS on three fixed MATH500 test examples using DeepSeek Flash. This is a partial reproduction, not the paper's full 100-example Llama3-8B-Instruct result.

## Result summary

| Condition | MCTS iterations | Correct | Mean runtime per 3-question run | Mean tokens per run |
|---|---:|---:|---:|---:|
| Baseline | 10 | 9/9 | 97.0 s | 45,741 |
| Modified | 5 | 9/9 | 105.3 s | 46,707 |

The lower cap did not reduce work because the default early-stop setting ended each example after the first MCTS iteration. See `results/summary.csv` for per-trial data.

## Files

- `run_experiment.sh`: runs both conditions for three trials each.
- `QUICKSTART_REPRO.md`: setup and execution instructions.
- `REPORT_DRAFT.md`: complete written report.
- `PRESENTATION_SCRIPT.md`: talk track and screen-recording directions.
- `output/pdf/FTEC5660_LiTS_Reproducibility_Report.pdf`: formatted report.
- `results/summary.csv`: measured accuracy, time, token totals, and API call counts.

## Reproduce

See `QUICKSTART_REPRO.md`. Set `OPENAI_API_KEY` and `OPENAI_API_BASE` in a local `.env` file; never commit API credentials. The run script verifies the fixed dataset subset before making API calls.

Original implementation: https://github.com/xinzhel/lits-llm
Paper: https://arxiv.org/abs/2603.00631
