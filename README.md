# claude-actions-lab

Sandbox repo for testing the "CI-Failure Repair Loop" agent automation recipe.

## What's here

- `.github/workflows/ci.yml` — trivial CI job (`npm test`) that can pass or fail.
- `.github/workflows/ci-repair.yml` — triggers when CI fails, runs Claude Code
  (bounded to 15 turns) to diagnose and push a fix to a `ci-repair/<run-id>` branch.

## Setup required

Add a repo secret before this will run:

```
gh secret set ANTHROPIC_API_KEY
```

Then break `sample.test.js` and push to `main` to see the repair loop trigger.
