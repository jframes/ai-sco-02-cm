# CLAUDE.md

@~/.claude/profiles/sco-02-cm/profile.md

## This workspace

This folder is a **ticket workspace** of the SCO-02 Configuration Management role. It is a
checkout of the private `ai-sco-02-cm` repository (AI metadata only); the folder name is the Jira
ticket key in lowercase (e.g. `xmminssocops-264` → `XMMINSSOCOPS-264`). Read that ticket with the
`jira-issues` skill before planning. The mission is in `.mission`; the work repositories listed
in `missions/<mission>.repos` are cloned next to this file by `bootstrap.sh` and are ignored by
this repository's `.gitignore`.

Commit messages: work repositories use the ticket key (`XMMINSSOCOPS-264: ...`); changes to this
AI repository carry no Jira ID.

## Mission `xmm` — XMM SOC (XRPS)

- **`wa01_xips_extended_frontend`**, **`wa01_xips_extended_backend`** (`xmmsoc/…`) — XRPS source
  code, owned by the XRPS team. Read them to learn how they build; do not add CI or AI files
  to them.
- **`wa02_xmmsoc_ci`** (`xmmsoc/wa02_xmmsoc_ci`) — central CI repository of the `xmmsoc` Bitbucket project:
  Harness pipeline YAML, one folder per product, imported into Harness project `SCI/XMMSOC`
  through Git Experience. All pipeline work for XRPS lands here.

## Mission `cmsup` — CM SUP transversal repositories

- **`kind`** (`cmsup/kind`) — local Kubernetes clusters with Kustomize overlays.

## AI files in this workspace

- `CLAUDE.md` (this file) — applies to every repository below it.
- `claude-md/<repo>/CLAUDE.md` — guidance for one work repository; `bootstrap.sh` links it into
  the repository and hides it through `.git/info/exclude`. Never write a `CLAUDE.md` directly
  into a work repository.
- `.claude/skills/` — skills specific to this role's projects (general ones live in
  `ai-user-config`).
