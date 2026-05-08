# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

NodeJS-ReadmeGenerator is a command-line Node.js application that prompts the user for project information via Inquirer and generates a professional `README.md` file. The project is currently a starter scaffold — most functions are stubbed out with `TODO` comments and need implementation (question prompts, license badge/link/section rendering, file writing, and app initialization).

## Tech Stack

- Language: JavaScript (Node.js, ES modules — `index.js` uses `import`)
- Runtime: Node.js
- Dependencies: `inquirer` ^8.2.4 (interactive CLI prompts)
- No build, lint, or test tooling configured

## Repository Structure

```
NodeJS-ReadmeGenerator/
├── index.js                    # Entry point — Inquirer prompts + init() + writeToFile()
├── utils/
│   └── generateMarkdown.js     # Builds README markdown string from answers; license helpers
├── package.json                # Declares inquirer dependency only (no scripts, no name/version)
├── package-lock.json
└── README.md                   # Currently just the project title
```

## Common Development Commands

```bash
# Install dependencies
npm install

# Run the generator
node index.js
```

No `test`, `lint`, or `build` scripts are defined in `package.json`.

## Key Files

- `index.js` — application entry point; holds the questions array and `init()`
- `utils/generateMarkdown.js` — markdown template + license rendering helpers
- `package.json` — minimal manifest (only `dependencies`)

## Notes

- Module system mismatch: `index.js` uses ESM `import` syntax, but `utils/generateMarkdown.js` uses CommonJS `module.exports`, and `package.json` has no `"type": "module"`. This will fail at runtime until reconciled (add `"type": "module"` and convert the export, or switch `index.js` to `require`).
- All core logic is unimplemented stubs — treat this repo as a scaffold to fill in, not a working tool.
- `package.json` is missing `name`, `version`, `scripts`, and `main` fields; add them when productionizing.
