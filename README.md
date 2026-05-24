# Default Agency

Planned reference starter pack — the team Clawie will ship by default once
spec 016 (the end-to-end software agency pipeline) enters delivery. This
repo currently holds the design contract only; the agent submodules,
flow definitions, and budget files described below have not yet been
authored.

> **Status:** Pending. v1.0 ships the substrate (durable lifecycle, container
> execution, policy, audit, teams, scheduler); the default agency lands in
> a v1.x release. See [spec 016](https://github.com/clawie-dev/specs/tree/main/speckit/016-software-agency-pipeline)
> and [spec 013](https://github.com/clawie-dev/specs/tree/main/speckit/013-team-orchestration-orgchart)
> for the design contract this repo will implement.

## Planned roles (9 agents)

| Role | Owns pipeline stage(s) |
|---|---|
| Researcher | research |
| Architect | spec, architecture |
| Coder | scaffold, implement |
| Reviewer | code-review, e2e-test |
| Security | security-review |
| Perf | performance-review |
| Doc-writer | documentation |
| DevOps | devops-setup, deploy-staging, deploy-production |
| Marketer | marketing-site, launch-announcement |

## Planned layout

```
default-agency/
├── team.yaml             # roles, charter
├── flows.yaml            # pipeline stage → role mapping
├── budgets.yaml          # default budgets
├── policies/             # team-wide policies
├── task-management.yaml  # OPTIONAL: Linear/Jira mapping (spec 026)
├── agents/               # 9 agent submodules (one per role)
└── README.md
```

Each agent submodule will follow [spec 008](https://github.com/clawie-dev/specs/tree/main/speckit/008-agent-definition):
`SOUL.md`, `AGENTS.yaml`, `TOOLS.yaml`, `MODEL.yaml`, `benchmarks/`,
`skills/`, `prompts/`.

## Use today (without this repo)

You can already build a multi-agent team on top of Clawie's v1.0 substrate
without waiting for this default pack:

```bash
# 1. Create a team in your Clawie instance
node ace teams:create my-agency

# 2. For each agent you want in the team, hydrate it from a directory
#    that contains SOUL.md, AGENTS.yaml, TOOLS.yaml:
node ace agents:load ./agents/coder
node ace agents:load ./agents/reviewer
# ...

# 3. Sync the team's egress rules to Outcall (Linux only)
node ace outcall:sync --team my-agency
```

The v1.x release that lands `default-agency/` will provide the nine
agent definitions above as ready-to-load directories.

## License

MIT — see [LICENSE](LICENSE).
