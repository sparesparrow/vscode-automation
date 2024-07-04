# Automated TICS Violations Fixing

## Overview

This VS Code extension allows automated TICS analysis and code violations resolution using the TICS tool, OpenAI API, and Git API. The user can run TICS analysis and fix violations either on their repository codebase or on a locally cloned repository.

## Features

- Run TICS analysis
- Fix TICS violations automatically
- Integration with OpenAI for suggested fixes
- Git integration for pushing changes

## Commands

- `extension.runTicsAnalysis`: Runs TICS analysis
- `extension.fixTicsViolations`: Fixes TICS violations

## Setup

1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Open the project in VS Code.
4. Press `F5` to start debugging the extension.

## Usage

1. Run the `Run TICS Analysis` command to analyze the code.
2. Run the `Fix TICS Violations` command to automatically fix any violations found.

## Configuration

Configure the extension in the settings:

- `tics.apiUrl`: The URL for the TICS API.
- `openai.apiKey`: The API key for OpenAI.
- `git.repoUrl`: The URL of the Git repository.

## License

MIT
