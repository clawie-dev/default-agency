# Default Agency

Reference starter pack — the team installed by default when you `clawie repo init`. Implements the end-to-end software agency pipeline from [spec 016](https://github.com/clawie-dev/specs/tree/main/speckit/016-software-agency-pipeline).

## Roles (9 agents)

| Role | Submodule | Owns pipeline stage(s) |
|---|---|---|
| Researcher | `agents/researcher/` | research |
| Architect | `agents/architect/` | spec, architecture |
| Coder | `agents/coder/` | scaffold, implement |
| Reviewer | `agents/reviewer/` | code-review, e2e-test |
| Security | `agents/security/` | security-review |
| Perf | `agents/perf/` | performance-review |
| Doc-writer | `agents/doc-writer/` | documentation |
| DevOps | `agents/devops/` | devops-setup, deploy-staging, deploy-production |
| Marketer | `agents/marketer/` | marketing-site, launch-announcement |

## Install

```bash
clawie team install clawie-dev/default-agency
```

This makes it a submodule under `teams/default-agency/` in your root config repo. Fork it once and customize:

```bash
clawie team fork clawie-dev/default-agency --as my-agency
```

## Layout

```
default-agency/
├── team.yaml             # roles, charter
├── flows.yaml            # pipeline stage → role mapping
├── budgets.yaml          # default budgets
├── policies/             # team-wide policies
├── task-management.yaml  # OPTIONAL: Linear/Jira mapping (spec 026)
├── agents/               # 9 agent submodules
└── README.md
```

Each agent submodule follows [spec 008](https://github.com/clawie-dev/specs/tree/main/speckit/008-agent-definition): SOUL.md, AGENTS.md, TOOLS.md, MODEL.yaml, benchmarks/, skills/, prompts/.

## Status

Bootstrap pending. See [`clawie-dev/specs/speckit/013-team-orchestration-orgchart`](https://github.com/clawie-dev/specs/tree/main/speckit/013-team-orchestration-orgchart) for the spec.

## License

MIT — see [LICENSE](LICENSE).
