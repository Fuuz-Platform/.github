# Contributing to Fuuz

Thank you for your interest in contributing to the Fuuz Industrial Intelligence Platform. Whether you're fixing a bug, improving documentation, or proposing a new feature, we appreciate your time and effort.

This guide will help you get started.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Commit Messages](#commit-messages)
- [Pull Requests](#pull-requests)
- [Issue Reporting](#issue-reporting)
- [Developer Certificate of Origin](#developer-certificate-of-origin)
- [Coding Standards](#coding-standards)
- [Documentation](#documentation)
- [Community](#community)

---

## Code of Conduct

By participating in this project, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). We are committed to providing a welcoming and inclusive experience for everyone. Please be respectful, constructive, and professional in all interactions.

---

## How Can I Contribute?

There are many ways to contribute, and not all of them require writing code:

- **Report bugs** — Found something broken? Open an issue and help us fix it.
- **Suggest features** — Have an idea that would improve the platform? We want to hear it.
- **Improve documentation** — Typos, unclear explanations, missing examples — all fair game.
- **Submit code changes** — Bug fixes, performance improvements, and new capabilities.
- **Write examples** — Sample applications, integration patterns, and how-to guides help the whole community.
- **Review pull requests** — Fresh eyes catch things the author missed. Reviews are incredibly valuable.
- **Answer questions** — Help other community members in discussions and issues.

If you're not sure where to start, look for issues labeled **`good first issue`** or **`help wanted`**.

---

## Getting Started

### Prerequisites

Before contributing, make sure you have:

- A [GitHub account](https://github.com/signup)
- [Git](https://git-scm.com/) installed and configured
- [Node.js](https://nodejs.org/) (LTS version recommended)
- Familiarity with the [Fuuz platform documentation](https://fuuz.com/docs)

### Fork and Clone

1. **Fork** the repository you want to contribute to by clicking the Fork button on GitHub.

2. **Clone** your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/REPO-NAME.git
   cd REPO-NAME
   ```

3. **Add the upstream remote** so you can keep your fork in sync:
   ```bash
   git remote add upstream https://github.com/fuuz/REPO-NAME.git
   ```

4. **Install dependencies:**
   ```bash
   npm install
   ```

---

## Development Workflow

We use **GitHub Flow** — a simple branching model built around `main` and short-lived feature branches.

### The Process

```
main (always deployable)
 └── feature/your-branch-name (your work happens here)
      └── Pull Request → Code Review → Merge → Delete branch
```

### Step by Step

1. **Sync your fork** with the latest upstream changes:
   ```bash
   git checkout main
   git fetch upstream
   git merge upstream/main
   ```

2. **Create a feature branch** from `main`:
   ```bash
   git checkout -b feature/short-description
   ```

   Use a descriptive branch name. Prefixes help categorize the work:

   | Prefix | Use For |
   |--------|---------|
   | `feature/` | New functionality |
   | `fix/` | Bug fixes |
   | `docs/` | Documentation changes |
   | `refactor/` | Code restructuring (no behavior change) |
   | `test/` | Adding or updating tests |
   | `chore/` | Build config, dependencies, housekeeping |

3. **Make your changes** in small, focused commits (see [Commit Messages](#commit-messages) below).

4. **Push your branch** to your fork:
   ```bash
   git push origin feature/short-description
   ```

5. **Open a Pull Request** against `main` on the upstream repository.

### Keeping Your Branch Up to Date

If `main` has moved ahead while you're working, rebase your branch to keep history clean:

```bash
git fetch upstream
git rebase upstream/main
```

Resolve any conflicts, then force-push your branch:

```bash
git push origin feature/short-description --force-with-lease
```

---

## Commit Messages

We use **Conventional Commits** — a structured format that makes commit history readable and enables automated changelog generation.

### Format

```
<type>(<scope>): <short description>

<optional body>

<optional footer>
Signed-off-by: Your Name <your.email@example.com>
```

### Types

| Type | When to Use |
|------|-------------|
| `feat` | A new feature or capability |
| `fix` | A bug fix |
| `docs` | Documentation only changes |
| `style` | Formatting, whitespace, semicolons (no logic changes) |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `test` | Adding or correcting tests |
| `chore` | Build process, tooling, or dependency updates |
| `perf` | Performance improvement |
| `ci` | CI/CD configuration changes |

### Examples

```
feat(connectors): add support for Oracle ERP Cloud connector

fix(gateway): resolve Modbus TCP reconnection timeout on network interruption

docs(readme): update deployment instructions for v2.3

refactor(flows): extract common JSONata transform utilities into shared module
```

### Linking to Jira

If your contribution relates to an internal Fuuz Jira ticket, include the reference in the commit body or footer:

```
fix(oee): correct shift boundary calculation for overnight shifts

Resolves FUUZ-1234
```

This is optional for external contributors but encouraged for Fuuz team members and partners.

### Sign Your Commits

All commits must include a DCO sign-off (see [Developer Certificate of Origin](#developer-certificate-of-origin)). Add the `-s` flag when committing:

```bash
git commit -s -m "feat(models): add batch record data model"
```

---

## Pull Requests

### Before You Submit

- [ ] Your branch is up to date with `main`
- [ ] Your code follows the [coding standards](#coding-standards)
- [ ] You have added or updated tests where applicable
- [ ] You have updated documentation if your change affects public APIs or behavior
- [ ] All existing tests pass
- [ ] Every commit is signed off (DCO)

### PR Description

When opening a pull request, please include:

- **What** — A clear summary of what the PR does
- **Why** — The motivation or problem it solves
- **How** — A brief explanation of the approach (especially for non-trivial changes)
- **Testing** — How you verified the change works
- **Screenshots** — If the change affects the UI

Use the PR template if one is provided in the repository.

### Review Process

1. At least **one maintainer approval** is required before merging.
2. Reviewers may request changes — this is normal and collaborative, not adversarial.
3. Address review feedback by pushing additional commits to your branch. Don't force-push during review unless asked — it makes it harder for reviewers to see what changed.
4. Once approved, a maintainer will merge your PR using **squash and merge** to keep `main` history clean.

### Response Times

We aim to provide initial feedback on PRs within **5 business days**. Complex changes may take longer. If you haven't heard back after a week, feel free to leave a polite comment on the PR.

---

## Issue Reporting

We track work internally using **Atlassian Jira**, but we use **GitHub Issues** for public bug reports and feature requests.

### Bug Reports

When filing a bug, include:

- **Environment** — Fuuz platform version, browser, OS, gateway version (if applicable)
- **Steps to reproduce** — A clear, numbered sequence to trigger the issue
- **Expected behavior** — What you expected to happen
- **Actual behavior** — What actually happened
- **Screenshots or logs** — If available, these are extremely helpful
- **Severity** — Is the issue a crash, data loss, incorrect behavior, or cosmetic?

### Feature Requests

When suggesting a feature:

- **Problem statement** — What challenge are you facing?
- **Proposed solution** — How do you think it should work?
- **Alternatives considered** — Have you tried other approaches?
- **Use case** — Who benefits and in what scenario?

### Labels

Maintainers will triage and label issues. Common labels include:

| Label | Meaning |
|-------|---------|
| `bug` | Confirmed defect |
| `enhancement` | Feature request |
| `good first issue` | Suitable for new contributors |
| `help wanted` | Community contributions welcome |
| `documentation` | Docs improvement needed |
| `question` | Needs clarification before action |
| `wontfix` | Decided not to address |
| `duplicate` | Already tracked elsewhere |

---

## Developer Certificate of Origin

We use the **Developer Certificate of Origin (DCO)** to ensure that all contributions are made with the legal right to do so. The DCO is a lightweight alternative to a full Contributor License Agreement and is the same mechanism used by the Linux kernel, Kubernetes, and many other major open-source projects.

By signing off on your commits, you certify that you wrote the code (or have the right to submit it) and that you are granting Fuuz and the community the right to use it under the project's license.

### The DCO Text

```
Developer Certificate of Origin
Version 1.1

Copyright (C) 2004, 2006 The Linux Foundation and its contributors.

By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

### How to Sign Off

Add the `-s` flag to your git commit command:

```bash
git commit -s -m "your commit message"
```

This automatically appends a `Signed-off-by` line with your name and email:

```
Signed-off-by: Jane Smith <jane.smith@example.com>
```

Make sure your `git config user.name` and `git config user.email` are set correctly:

```bash
git config --global user.name "Your Full Name"
git config --global user.email "your.email@example.com"
```

If you forget to sign off, you can amend your most recent commit:

```bash
git commit --amend -s --no-edit
```

Or sign off on multiple commits with an interactive rebase:

```bash
git rebase --signoff HEAD~3
```

**Pull requests with unsigned commits will not be merged.**

---

## Coding Standards

### General Principles

- **Clarity over cleverness** — Write code that is easy to read and maintain. Industrial systems are maintained for years; clever shortcuts become expensive.
- **Small, focused changes** — Each PR should do one thing well. If you find yourself writing "and" in the PR description, consider splitting it.
- **Test what matters** — Cover the critical paths and edge cases. Tests should give confidence to ship, not slow development to a crawl.
- **Document the "why"** — Code shows what happens; comments should explain why a decision was made.

### JavaScript / Node.js

- Use `"use strict"` in all files
- Prefer `const` over `let`; avoid `var`
- Use meaningful variable names — `workcenterState` not `ws`
- Handle errors explicitly — no silent `catch` blocks
- Use async/await over raw promises where possible

### JSONata (Fuuz Expressions)

- Capture context variables at the top of complex expressions: `( $data := $; ... )`
- Use `$not()` function, never the `!` operator (not supported)
- Use `=` for comparison, not `==` or `===`
- Use `&` for string concatenation, not `+`
- Comment complex transforms with surrounding context about inputs and expected outputs

### GraphQL

- Always specify the API explicitly: `"api": "application"` or `"api": "system"`
- Use `first:` parameter to limit result sets — never query without pagination
- Traverse results with `$.modelName.edges[*].node` pattern

### Fuuz Packages

- Every package must include a valid `manifest.json` with version and platform compatibility
- Use UUID v4 for all identifiers — never reuse IDs from examples or documentation
- Follow deployment ordering: ModuleGroup → Module → Sequences → Data Models → Seed Data → Screens/Flows

---

## Documentation

Good documentation is just as important as good code. When contributing:

- **Update docs with code changes** — If your change affects how something works, update the relevant documentation in the same PR.
- **Use clear, simple language** — Our community includes non-native English speakers and people from a wide range of technical backgrounds.
- **Include examples** — A concrete example is worth a thousand words of explanation.
- **Keep formatting consistent** — Use Markdown. Follow the structure and conventions of existing docs.

---

## Community

- **GitHub Issues** — For bug reports, feature requests, and public discussion
- **GitHub Discussions** — For questions, ideas, and general conversation (if enabled on the repo)
- **Fuuz Documentation** — [fuuz.com/docs](https://fuuz.com/docs)
- **Website** — [fuuz.com](https://fuuz.com)

---

## Recognition

All contributors are recognized in our release notes. Significant contributions may be highlighted on the Fuuz blog and community channels. We believe in giving credit where it's due.

---

## Questions?

If anything in this guide is unclear, open an issue with the `question` label or start a discussion. We're happy to help you get started.

---

<p align="center">
  <strong>Thank you for helping build the future of industrial intelligence.</strong><br/>
  <a href="https://fuuz.com">fuuz.com</a>
</p>
