# vscode-automation — automated TICS violation fixing

A VS Code extension that runs [TICS](https://www.tiobe.com/tics/) code-quality analysis on a C++ code
base and uses the OpenAI API to propose and apply fixes for the reported violations, then hands the
result to Git as a reviewable change.

It was built in 2024 during an innovation sprint on a client engagement (electron-microscopy detector
software) and presented to the development team and stakeholders at the end of the sprint.

> **Source code:** the extension was developed inside the client's environment and its source is not
> published in this repository. This page documents what it did and how it worked.

## What it did

1. **Analyse.** Ran TICS on the open workspace or on a locally cloned repository and collected the
   violations (rule, file, line, message).
2. **Propose.** For each violation, sent the rule description and the surrounding code to the OpenAI
   API and asked for a minimal fix that satisfies the rule without changing behaviour.
3. **Apply and review.** Applied the suggested edits in the editor so the developer could inspect each
   diff, then committed the accepted fixes on a branch through the Git API, ready for a pull request.

## Commands

| Command | Purpose |
|---|---|
| `Run TICS Analysis` (`extension.runTicsAnalysis`) | Run TICS and list the violations |
| `Fix TICS Violations` (`extension.fixTicsViolations`) | Generate, apply and commit AI-suggested fixes |

## Configuration

| Setting | Meaning |
|---|---|
| `tics.apiUrl` | URL of the TICS server API |
| `openai.apiKey` | OpenAI API key used for fix suggestions |
| `git.repoUrl` | Repository the fixes are pushed to |

## Built with

TypeScript, the VS Code Extension API, the Git API and the OpenAI API.

## License

MIT (see [LICENSE](LICENSE)).
