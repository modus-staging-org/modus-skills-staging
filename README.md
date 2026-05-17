# Modus Skills & Agents

This repository is the **source of truth** for your organization's
[Modus](https://modus.com) Skills and Agents.

## Layout

- `.modus/manifest.yaml` — repo metadata, last-applied commit, slug renames
- `.modus/skills/<slug>.yaml` — one Skill per file
- `.modus/agents/<slug>.yaml` — one Agent per file
- `.github/workflows/validate-modus-manifests.yml` — CI validator

## Editing

1. Open a pull request against `main` with your changes.
2. The `Validate Modus Manifests` check enforces the schema — merging is
   blocked while it fails.
3. After merge, Modus pulls the new state into Postgres and reconciles any
   downstream resources (Temporal Schedules for Agents).

Drafts you create in the Modus UI stay in Postgres until you Deploy. On
Deploy, Modus commits the published YAML to this repo's `main`.

## How to connect

1. Fork this repo to a GitHub account/org that has the Modus GitHub App
   installed (your IT admin sets that up via the Integrations page in
   Modus).
2. In Modus, open the org modal → Git Sync tab → "I forked it — check now".
