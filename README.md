# Red Team Report

Promptfoo-based red team evaluation for an AI customer support agent.

Repository: https://github.com/stevenleon30/red-team-report

This project tests a customer support system prompt against three attack categories:

- Prompt injection
- Jailbreak attempts
- Scope boundary violations

## Project Structure

- `attacks/prompt-injection.yaml` - prompt injection test cases
- `attacks/jailbreaks.yaml` - jailbreak test cases
- `attacks/scope-boundary.yaml` - scope boundary test cases
- `RED-TEAM-REPORT.md` - full written report
- `RED-TEAM-EXECUTIVE-SUMMARY.md` - short summary report

## Requirements

- Node.js 20 or newer
- An Anthropic API key

## Setup

1. Install dependencies:

```bash
npm install
```

2. Create a local environment file if you do not already have one:

```bash
cp .env.example .env
```

3. Add your Anthropic API key to `.env`:

```bash
ANTHROPIC_API_KEY=your-key-here
```

## Run Evaluations

Run a single eval:

```bash
npx promptfoo eval --config attacks/prompt-injection.yaml
```

Run the other configs:

```bash
npx promptfoo eval --config attacks/jailbreaks.yaml
npx promptfoo eval --config attacks/scope-boundary.yaml
```

## Reports

After running Promptfoo, open the generated report link in the terminal output. The full write-up is in `RED-TEAM-REPORT.md`, and the short version is in `RED-TEAM-EXECUTIVE-SUMMARY.md`.

## GitHub Actions

This repo includes a workflow that runs all three Promptfoo configs on push and pull request.

To make it work in GitHub:

1. Add a repository secret named `ANTHROPIC_API_KEY`.
2. Push your changes.
3. Check the Actions tab for results.