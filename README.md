# ai-sco-02-cm

AI workspace files for the **SCO-02 Configuration Management** role (`sco-02-cm` profile):
workspace instructions, the list of work repositories per mission, per-repository guidance and
project skills. Kept apart from the work repositories so nothing here is ever committed into them.

## Create a ticket workspace

```bash
~/workspace/sco-02/ai-cm/ai-user-config/scripts/new-workspace.sh sco-02-cm <TICKET> --mission <mission>
# e.g. … sco-02-cm XMMINSSOCOPS-264 --mission xmm  →  ~/workspace/sco-02/cm/xmm/xmminssocops-264/
```

That clones this repository as the ticket folder and runs `./bootstrap.sh <mission>`, which
installs the user-level configuration, clones the mission's work repositories and wires their
`CLAUDE.md` files. `bootstrap.sh` is safe to re-run (e.g. after a repository has been created).

## Layout

| Path | Purpose |
|------|---------|
| `CLAUDE.md` | workspace instructions; imports the role profile |
| `missions/<mission>.repos` | work repositories of a mission: name, URL, branch |
| `claude-md/<repo>/CLAUDE.md` | guidance for one work repository, linked in by `bootstrap.sh` |
| `.claude/skills/` | project-level skills |

## Add a mission or a repository

Add a line to `missions/<mission>.repos` (or a new file), describe it in `CLAUDE.md`, and add the
mission to `ai-user-config/profiles/sco-02-cm/profile.yaml`.
