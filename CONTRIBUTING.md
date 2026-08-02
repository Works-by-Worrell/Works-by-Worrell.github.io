# Contributing to Works-by-Worrell Public Site (`Works-by-Worrell.github.io`)

This document outlines the branch taxonomy, commit message standards, and workflows specifically for the **Works-by-Worrell.github.io** public web profile repository.

---

## 1. Branch Strategy & Taxonomy

All development work MUST occur on a feature or task branch before targeting the `main` branch. All branches MUST align with one of the following prefix categories:

### Branch Prefix Categories
*   `feat/` - Web page delivery (e.g. adding portfolio sections, updating styles)
*   `fix/` - Immediate bug triage, HTML/CSS layout corrections, or rendering fixes
*   `docs/` - Runbook updates, setup guides, and repository README documentation
*   `chore/` - Maintenance, dependency updates, and workspace configuration adjustments

### Branch Naming Convention
All branches MUST follow this format: 
`<type>/issue-<id>-<description>` or `<type>/phase<num>-<short-description>`

**Examples:**
*   `feat/phase5-add-portfolio-links`
*   `fix/issue-3-mobile-responsiveness`
*   `docs/issue-3-readme-web`

---

## 2. Commit Message Conventions

We strictly adhere to the [Conventional Commits](https://www.conventionalcommits.org/) specification. This enables automated release notes, changelog generation, and clear system auditability.

### Commit Format
Commit messages MUST follow the structure:
```
<type>(<scope>): <short description> (#<issue-number>)

[Optional body explaining design rationale or context]
```
*Note: A git validation hook is configured to enforce that all commit messages end with a parenthesized issue reference (e.g. `(#3)`).*

### Scope Boundaries (Repository Specific)
When writing a commit, the `scope` MUST represent the logical area of this web repository:

| Scope | Logical Domain | Example |
| :--- | :--- | :--- |
| `web` | HTML and CSS frontend code and structure | `feat(web): add responsive flexbox grid layout (#3)` |
| `asset` | Images, SVG files, and custom logos | `chore(asset): compress branding image assets (#3)` |
| `cname` | CNAME records and domain ingress modifications | `infra(cname): update custom domain references (#3)` |
| `gov` | Governance, blueprints, templates, or repository setup | `docs(gov): write readme guidelines for layout (#3)` |

---

## 3. Local Git Hook Installation

To enforce these formatting rules locally and prevent commit aborts, you MUST configure your local repository to execute the shared git validation hook:

```bash
git config core.hooksPath .githooks
```
Once configured, the script [.githooks/commit-msg](.githooks/commit-msg) will run automatically before every commit to validate the message format.
