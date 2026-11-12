# Contributing to Mandate

Thanks for your interest. Mandate is an educational hackathon project, but it holds a firm line: **no number shown to a trustee comes from an LLM, and no claim is trusted until code has verified it.**

## Set up

Follow the [Quickstart](README.MD#quickstart). The four starred demo scenarios under **Research stock** work without any API keys, so you can check most UI changes offline.

## Before you open a pull request

Run the same checks as CI:

```powershell
npm --prefix frontend run build
npm --prefix frontend test
.venv\Scripts\python -m unittest tests.test_integration quant.test_stats quant.test_portfolio -v
```

## Rules a change must keep

- **Numbers come from data or code**, never from a model.
- **Every agent claim cites source IDs**, and `mandate/verify.py` checks them. Unverified claims are flagged, never trusted.
- **The ethics veto stays in code.** A verified FAIL must always reject, whatever the Chair says.
- **LLM output is validated with pydantic** and cached on disk.
- **No fake data.** Missing measurements are `null` or an explicit error. Test doubles stay inside the test suite.
- **Secrets live only in `.env`**, which is ignored by Git. Run `git status` before you commit.

## Branches

`main` should always build. Work on a branch, keep pull requests focused, and say what you tested.
