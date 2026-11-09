# Contributing to Adalbird Labs projects

Project-specific contribution rules always take precedence over this default.

## Working model

1. Start from a clear problem, requirement or issue.
2. Keep changes focused and small enough to review safely.
3. Add or update tests for changed behavior.
4. Run the repository's verification commands before requesting review.
5. Update documentation when behavior, architecture, release steps or user-facing behavior changes.
6. Use a pull request for non-trivial changes unless the repository documents a different workflow.

## Quality and safety

- Do not commit passwords, API keys, private tokens or production secrets.
- Treat personal, location and user-generated data as sensitive by default.
- Do not weaken validation, authorization, privacy controls or release gates to make a test pass.
- Prefer deterministic automated checks over undocumented manual assumptions.
- Keep dependency changes deliberate and review security impact when introducing new packages.

## Pull requests

A pull request should explain what changed, why it changed, how it was verified and any relevant risks or follow-up work.

For security vulnerabilities, do not open a public issue. Follow `SECURITY.md` instead.
