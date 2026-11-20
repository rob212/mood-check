# Mood Check

A deliberately small TypeScript web app used to learn a best-practice CI/CD pipeline and quality engineering on AWS. The pipeline is the point; the app stays simple.

This is a series I am blogging about, follow along in my [Medium series](https://medium.com/@robert_mcbryde/building-a-ci-cd-part-1-a-tested-hello-world-f42d835b73d3)

## Prerequisites

- Node.js, at the version in `.nvmrc` (24). I use [mise](https://mise.jdx.dev/) to install it.
- [gitleaks](https://github.com/gitleaks/gitleaks), used by the pre-commit hook: `brew install gitleaks`
- [Semgrep](https://semgrep.dev/) 1.186.0, used for SAST: `brew install pipx && pipx ensurepath`, open a new terminal, then `pipx install semgrep==1.186.0`

## Setup

```bash
npm ci
```

This installs dependencies from the lockfile and sets up the Husky pre-commit hook.

## Checks

```bash
npm test               # unit tests
npm run lint           # ESLint, fails on warnings
npm run format:check   # Prettier, checks without changing files
npm run build          # type-check and bundle every workspace
npm run sast           # Semgrep static analysis, fails on any finding
```

## Licence

MIT
