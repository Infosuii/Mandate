## What this changes

<!-- One or two sentences. Link the issue: Closes #… -->

## How it was tested

- [ ] `npm --prefix frontend run build` and `npm --prefix frontend test` pass
- [ ] `python -m unittest tests.test_integration quant.test_stats quant.test_portfolio -v` passes
- [ ] Checked in the app (a ★ demo scenario or a live run)

## Guardrails

- [ ] No number shown to trustees comes from an LLM
- [ ] Agent claims still cite source IDs and pass through `verify.py`
- [ ] The ethics veto is still enforced in code
- [ ] No `.env`, keys or credentials committed
