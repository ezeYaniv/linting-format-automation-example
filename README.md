# Introduction

## Summary: What does this project do?

This is a default React app that integrates linting & formatting tools with git hooks.

## What technologies/skills/concepts does this project practice?

- ESLint
- Prettier
- lint-staged
- husky

## Under the hood: How does this project work?

1. Configuration files for ESLint and Prettier specify rules which will be followed for all users working on this project.
2. Husky is set up to run commands listed in '.husky/pre-commit' whenever a user runs 'git commit'.
3. Husky runs lint-staged, which intelligently targets only files which changed and are staged (with git add, for example).
4. lint-staged runs ESLint and Prettier on the staged files based on the configuration specified in 'package.json'.
5. If ESLint throws no errors, then the staged files are formatted according to Prettier rules and are actually committed.
6. Otherwise, terminal displays linting errors which user must fix before committing.

Note: .vscode/settings.json sets VSCode's default formatter for this project to Prettier, and allows reformatting on save. This is a user choice, as files will be formatted automatically through lint-staged even if user does not press Ctrl+S while working on a file.

Note 2: .prettierignore is a copy of gitignore

Note 3: .eslintcache is added to gitignore - it is an auto-generated build file which will appear as a changed file and block branch switching

## Current status: What should future me know about where this project left off?

Potential next steps:

- Add more git hooks to .husky folder for practice
- Change lint-staged properties in 'package.json' to include other file formats (json?)
