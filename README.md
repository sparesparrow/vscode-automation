# vscode-automation — automated TICS violation fixing

A VS Code extension that runs [TICS](https://www.tiobe.com/tics/) code-quality analysis on a C++ code
base and uses the OpenAI API to fix the reported violations, then pushes
the changes through Git.

It was built in 2024 during an innovation sprint on a client engagement (electron-microscopy detector
software) and presented to the development team and stakeholders at the end of the sprint.

> **Source code:** the extension was developed inside the client's environment and its source is not
> published in this repository. This page documents what it did and how it worked.

## What it did

1. **Analyse.** Ran TICS on the open workspace or on a locally cloned repository and collected the
   reported violations.
2. **Fix.** Sent each violation with its code context to the OpenAI API and applied the suggested fix
   to the source.
3. **Deliver.** Pushed the resulting changes through the Git integration.

## Commands

| Command | Purpose |
|---|---|
| `Run TICS Analysis` (`extension.runTicsAnalysis`) | Run TICS and list the violations |
| `Fix TICS Violations` (`extension.fixTicsViolations`) | Fix the violations with AI-suggested changes |

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
